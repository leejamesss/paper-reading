# Visual ChatGPT                




## 作者和论文链接
- 《Visual ChatGPT: Talking, Drawing and Editing with Visual Foundation Models》，它是由 Chenfei Wu, Shengming Yin, Weizhen Qi, Xiaodong Wang, Zecheng Tang 和 Nan Duan 六位作者撰写的。这篇论文于 2023 年 3 月 8 日提交到了 arXiv 网站上，可以在 [arXiv.org](https://arxiv.org/abs/2303.04671) 上免费获取。

## 主要内容 
- 是关于 Visual ChatGPT 系统的。Visual ChatGPT 是一个结合了不同视觉基础模型的系统，它能够让用户与 ChatGPT 交互，不仅可以发送和接收语言，还可以发送和接收图像。它还能够处理复杂的视觉问题或视觉编辑指令，这些指令需要多个 AI 模型的多步协作，并且能够提供反馈并要求更正结果。实验表明，Visual ChatGPT 为研究 ChatGPT 的视觉角色提供了可能性。

## 涉及模型
- Visual ChatGPT 涉及到的模型包括 ChatGPT 和一系列视觉基础模型。ChatGPT 是一个语言模型，它能够与用户进行交互，具有出色的对话能力和推理能力。视觉基础模型则是一类在计算机视觉领域表现出色的模型，它们能够理解和生成复杂的图像。例如，BLIP 模型能够理解并描述图像，而 Stable Diffusion 模型则能够根据文本提示合成图像。

## 视觉基础模型
- 视觉基础模型（Visual Foundation Models，简称VFMs）是一类在计算机视觉领域表现出色的模型，它们能够理解和生成复杂的图像。然而，由于这些模型通常是针对特定任务设计的，并且输入输出格式固定，因此它们在人机交互方面不如会话语言模型灵活。

# Visual ChatGPT简介

## 系统
- 结合不同视觉基础模型
- 能够发送和接收语言和图像

## 功能
- 处理复杂的视觉问题或视觉编辑指令
- 需要多个 AI 模型的多步协作
- 能够提供反馈并要求更正结果

## 实验结果
- 为研究 ChatGPT 的视觉角色提供了可能性


## 相关视觉基础模型

### BLIP模型（图->文）
  - BLIP 是一个视觉语言预训练模型，它能够从有噪声的图像文本对中学习。BLIP 通过引导标题来有效地利用有噪声的网络数据，其中一个标题生成器生成合成标题，而一个过滤器则删除有噪声的标题。BLIP 在多种视觉语言任务上都取得了最先进的结果，例如图像文本检索、图像字幕和 VQA。

### Stable Diffusion模型（类似于镜头模糊再聚焦）（文->图）
  - Stable Diffusion 是一种生成模型，它能够根据文本提示合成图像。它基于扩散过程，通过在每个时间步骤中添加噪声来逐渐模糊图像，然后再通过条件扩散过程来逐渐恢复图像。Stable Diffusion 能够生成高质量、多样性丰富的图像。

### Pix2Pix模型(图->图)
#### 相关知识
  - Pix2Pix是一种条件生成对抗网络（cGAN）[注释](#cGAN)，它学习从输入图像到输出图像的映射。在Pix2Pix cGAN中，可以根据输入图像生成相应的输出图像。cGAN最初是在《Conditional Generative Adversarial Nets》（Mirza和Osindero，2014）中提出的
#### 本文角色
  - Pix2Pix是作为一种视觉基础模型（Visual Foundation Model）被用于Visual ChatGPT系统中的。它与其他视觉基础模型一起，通过Prompt Manager与ChatGPT进行交互，帮助ChatGPT处理复杂的视觉任务。但是，本文并未详细说明Pix2Pix在Visual ChatGPT系统中的具体应用方式。


### 模型应用
  - 在这篇论文中，Visual ChatGPT 系统结合了不同的视觉基础模型，包括 BLIP 和 Stable Diffusion 等，以实现对图像的理解和生成。这些模型能够协同工作，处理复杂的视觉问题或视觉编辑指令，并提供反馈和更正结果。

## 用户交互

### prompt manager（视觉基础模型和Visual ChatGPT的翻译官）
  - Visual ChatGPT 是一个结合了不同视觉基础模型的系统，它能够让用户与 ChatGPT 交互，不仅可以发送和接收语言，还可以发送和接收图像。它通过一个名为 Prompt Manager 的组件来连接 ChatGPT 和这些视觉基础模型。Prompt Manager 能够显式地告诉 ChatGPT 每个视觉基础模型的能力，并指定输入输出格式；它还能够将不同的视觉信息（例如 png 图像、深度图像和掩码矩阵）转换为语言格式，以帮助 ChatGPT 理解；此外，它还能够处理不同视觉基础模型的历史记录、优先级和冲突。
### 用户交互具体例子
  - 用户可以通过输入文本或上传图像与 Visual ChatGPT 系统进行交互。例如，用户可以上传一张黄色花朵的图片，并输入一条复杂的语言指令：“请根据这张图片预测的深度生成一朵红色花朵，然后将其变成卡通风格，一步一步地”。在 Prompt Manager 的帮助下，Visual ChatGPT 会启动一系列相关的视觉基础模型。在这种情况下，它首先应用深度估计模型来检测深度信息，然后利用深度到图像模型根据深度信息生成一幅红色花朵的图像，最后利用基于 Stable Diffusion 模型的风格转换 VFM 改变这幅图像的风格为卡通风格。在上述流程中，Prompt Manager 作为 ChatGPT 的调度器，提供视觉格式类型并记录信息转换过程。最后，当 Visual ChatGPT 从 Prompt Manager 获取“卡通”的提示时，它将结束执行流程并显示最终结果。


## 优势
- Visual ChatGPT具有灵活性。它不需要从头开始训练一个新的多模态ChatGPT，而是直接基于现有的ChatGPT构建，并结合多种视觉基础模型。如果我们想要结合超出语言和图像之外的其他模态（如视频或声音），则无需每次都训练一个全新的多模态模型。


# cGAN
- cGAN是一种基于生成对抗网络（GAN）的条件生成模型，全称为条件生成对抗网络（Conditional Generative Adversarial Networks）。与传统的GAN不同，cGAN在生成过程中引入了额外的条件信息，使得生成器能够根据给定的条件生成特定类型的图像或数据。
- 在训练过程中，cGAN将条件信息和随机噪声拼接在一起作为输入，同时也将目标数据（例如真实图像）与条件信息拼接在一起作为判别器的输入。生成器的输出会被判别器判断是否真实，并同时与目标数据计算损失函数。通过这种方式，生成器可以在给定条件下生成逼真的数据。
