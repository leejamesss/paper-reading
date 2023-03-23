# Visual ChatGPT

论文链接：[https://arxiv.org/abs/2303.04671](https://arxiv.org/abs/2303.04671)

题目:《Visual ChatGPT: Talking, Drawing and Editing with Visual Foundation Models》，它是由 Chenfei Wu, Shengming Yin, Weizhen Qi, Xiaodong Wang, Zecheng Tang 和 Nan Duan 六位作者撰写的。这篇论文于 2023 年 3 月 8 日提交到了 arXiv 网站上，可以在 [arXiv.org](https://arxiv.org/abs/2303.04671) 上免费获取。

主要内容:是关于 Visual ChatGPT 系统的。Visual ChatGPT 是一个结合了不同视觉基础模型的系统，它能够让用户与 ChatGPT 交互，不仅可以发送和接收语言，还可以发送和接收图像。它还能够处理复杂的视觉问题或视觉编辑指令，这些指令需要多个 AI 模型的多步协作，并且能够提供反馈并要求更正结果。实验表明，Visual ChatGPT 为研究 ChatGPT 的视觉角色提供了可能性。


Visual ChatGPT 涉及到的模型包括 ChatGPT 和一系列视觉基础模型。ChatGPT 是一个语言模型，它能够与用户进行交互，具有出色的对话能力和推理能力。视觉基础模型则是一类在计算机视觉领域表现出色的模型，它们能够理解和生成复杂的图像。例如，BLIP 模型能够理解并描述图像，而 Stable Diffusion 模型则能够根据文本提示合成图像。


# Visual ChatGPT

## 系统
- 结合不同视觉基础模型
- 能够发送和接收语言和图像

## 功能
- 处理复杂的视觉问题或视觉编辑指令
- 需要多个 AI 模型的多步协作
- 能够提供反馈并要求更正结果

## 实验结果
- 为研究 ChatGPT 的视觉角色提供了可能性


## 相关模型

### BLIP模型
  -BLIP 是一个视觉语言预训练模型，它能够从有噪声的图像文本对中学习。BLIP 通过引导标题来有效地利用有噪声的网络数据，其中一个标题生成器生成合成标题，而一个过滤器则删除有噪声的标题。BLIP 在多种视觉语言任务上都取得了最先进的结果，例如图像文本检索、图像字幕和 VQA。

### Stable Diffusion模型
  -Stable Diffusion 是一种生成模型，它能够根据文本提示合成图像。它基于扩散过程，通过在每个时间步骤中添加噪声来逐渐模糊图像，然后再通过条件扩散过程来逐渐恢复图像。Stable Diffusion 能够生成高质量、多样性丰富的图像。

### 模型应用
  -在这篇论文中，Visual ChatGPT 系统结合了不同的视觉基础模型，包括 BLIP 和 Stable Diffusion 等，以实现对图像的理解和生成。这些模型能够协同工作，处理复杂的视觉问题或视觉编辑指令，并提供反馈和更正结果。

## 用户交互

### prompt manager
Visual ChatGPT 是一个结合了不同视觉基础模型的系统，它能够让用户与 ChatGPT 交互，不仅可以发送和接收语言，还可以发送和接收图像。它通过一个名为 Prompt Manager 的组件来连接 ChatGPT 和这些视觉基础模型。Prompt Manager 能够显式地告诉 ChatGPT 每个视觉基础模型的能力，并指定输入输出格式；它还能够将不同的视觉信息（例如 png 图像、深度图像和掩码矩阵）转换为语言格式，以帮助 ChatGPT 理解；此外，它还能够处理不同视觉基础模型的历史记录、优先级和冲突。
### 用户交互具体例子
用户可以通过输入文本或上传图像与 Visual ChatGPT 系统进行交互。例如，用户可以上传一张黄色花朵的图片，并输入一条复杂的语言指令：“请根据这张图片预测的深度生成一朵红色花朵，然后将其变成卡通风格，一步一步地”。在 Prompt Manager 的帮助下，Visual ChatGPT 会启动一系列相关的视觉基础模型。在这种情况下，它首先应用深度估计模型来检测深度信息，然后利用深度到图像模型根据深度信息生成一幅红色花朵的图像，最后利用基于 Stable Diffusion 模型的风格转换 VFM 改变这幅图像的风格为卡通风格。在上述流程中，Prompt Manager 作为 ChatGPT 的调度器，提供视觉格式类型并记录信息转换过程。最后，当 Visual ChatGPT 从 Prompt Manager 获取“卡通”的提示时，它将结束执行流程并显示最终结果。
