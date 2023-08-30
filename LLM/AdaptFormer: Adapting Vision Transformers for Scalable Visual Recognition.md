代码地址：https://github.com/ShoufaChen/AdaptFormer

![image](https://github.com/leejamesss/paper-reading/assets/117844938/64417cad-04d5-4f89-bdbe-cd7f78ecb9c0)
![image](https://github.com/leejamesss/paper-reading/assets/117844938/ed3ffe1e-97f5-4b28-9b3d-23880d7f7669)
![image](https://github.com/leejamesss/paper-reading/assets/117844938/f5fa599d-b3b0-4f3a-a4c9-5e16158f31b9)
![image](https://github.com/leejamesss/paper-reading/assets/117844938/7bbcf99c-18a9-457d-a846-f158fef7a3b5)
![image](https://github.com/leejamesss/paper-reading/assets/117844938/7424b70d-3633-477f-b9ec-fee0d5668928)

# 1. 这篇论文的主要贡献是什么？


- 提出了一种有效的适应方法，即AdaptFormer，可以高效地将预训练的视觉变换器（ViT）模型适应于多种图像和视频识别任务，而无需更新原始的预训练参数。
- 设计了一个轻量级的模块，即AdaptMLP，可以并行地与原始的ViT模型中的前馈网络（FFN）相连，产生适应于目标任务的特征表示。
- 在五个图像和视频数据集上进行了广泛的实验，表明AdaptFormer在目标领域中大幅提高了ViT的性能。例如，在只更新1.5%额外参数的情况下，它分别在Something-Something v2和HMDB51上相对于完全微调模型提高了约10%和19%的准确率。


# 2. 这个贡献重要吗？为什么？

这篇文章的主要贡献是：

- 提出了一种有效的适应方法，即AdaptFormer，可以高效地将预训练的视觉变换器（ViT）模型适应于多种图像和视频识别任务，而无需更新原始的预训练参数。
- 设计了一个轻量级的模块，即AdaptMLP，可以并行地与原始的ViT模型中的前馈网络（FFN）相连，产生适应于目标任务的特征表示。
- 在五个图像和视频数据集上进行了广泛的实验，表明AdaptFormer在目标领域中大幅提高了ViT的性能。例如，在只更新1.5%额外参数的情况下，它分别在Something-Something v2和HMDB51上相对于完全微调模型提高了约10%和19%的准确率。

这些贡献是重要的，因为：

- 它们展示了一种新颖且有效的方式来利用Transformer在计算机视觉领域的潜力，而不需要消耗大量的计算资源和存储空间。
- 它们提高了ViT模型的通用性和可扩展性，使其能够适应不同的视觉任务和领域，而不会发生灾难性干扰或性能下降。
- 它们为未来探索更多高效微调方法和构建灵活而通用的Transformer模型提供了启发和基础。


# 3. 这篇论文的局限是什么？

- 它只在识别任务中应用了AdaptFormer，没有探索它在其他任务，如目标检测或语义分割中的效果。
- 它没有与其他基于Transformer的模型进行比较，如DeiT [79]，Swin Transformer [83]，T2T-ViT [90]等，只使用了原始的ViT [31]作为基线。
- 它没有分析AdaptFormer对不同数据集和任务的适应性，是否需要调整中间维度或缩放因子等超参数。
- 它没有考虑AdaptFormer对不同预训练方法的影响，如监督预训练，自监督预训练，多模态预训练等。


# 4. 根据这篇文章的结果，你得到什么启发？


- **AdaptFormer是一种有效的适应方法**，它可以高效地将预训练的视觉变换器（ViT）模型适应于多种图像和视频识别任务，而无需更新原始的预训练参数。它通过引入轻量级的模块，即AdaptMLP，来产生适应于目标任务的特征表示。
- **AdaptFormer具有通用性和可扩展性**，它可以插入到不同的变换器模型中，并适用于多种视觉任务。它在五个图像和视频数据集上进行了广泛的实验，表明AdaptFormer在目标领域中大幅提高了ViT的性能。¹[1]例如，在只更新1.5%额外参数的情况下，它分别在Something-Something v2和HMDB51上相对于完全微调模型提高了约10%和19%的准确率。
- **AdaptFormer有助于探索更高效的微调方法和构建更灵活而通用的变换器模型**，它为未来在计算机视觉领域应用变换器提供了启发和基础。它也展示了一种新颖且有效的方式来利用Transformer在计算机视觉领域的潜力，而不需要消耗大量的计算资源和存储空间。

- **基于变换器的模型的研究进展**：文章介绍了近年来在计算机视觉领域应用变换器的一些代表性工作，包括图像分类、目标检测、语义分割、视频理解、3D识别等任务。文章也总结了变换器模型的一些优势，如模型结构简单、效果好、可扩展性强等。
- **参数高效的微调方法的研究现状**：文章回顾了一些参数高效的微调方法，如适配器 [46, 70, 69]、P-Tuning [58, 62]、BitFit [92]、LoRA [47]等，它们可以在保留原始预训练参数的同时，通过引入少量额外参数来适应目标任务。文章也分析了这些方法的一些局限性，如缺乏跨领域适应性、缺乏对变换器模型的特定设计等。
- **AdaptFormer的提出和设计**：文章提出了一种新颖且有效的适应方法，即AdaptFormer，可以高效地将预训练的视觉变换器（ViT）模型适应于多种图像和视频识别任务，而无需更新原始的预训练参数。文章设计了一个轻量级的模块，即AdaptMLP，可以并行地与原始的ViT模型中的前馈网络（FFN）相连，产生适应于目标任务的特征表示。文章也介绍了AdaptFormer的实现细节和超参数选择。
- **AdaptFormer的实验结果和分析**：文章在五个图像和视频数据集上进行了广泛的实验，表明AdaptFormer在目标领域中大幅提高了ViT的性能。例如，在只更新1.5%额外参数的情况下，它分别在Something-Something v2和HMDB51上相对于完全微调模型提高了约10%和19%的准确率。文章也与其他参数高效的微调方法进行了比较，如VPT [51]，并分析了AdaptFormer的优势和局限性。



# 5. 这篇论文的研究假设是什么？这些假设是否合理、局限或过于简化？

这篇论文的研究假设有以下几点：

- 预训练的视觉变换器（ViT）模型可以通过引入少量额外参数来适应多种图像和视频识别任务，而无需更新原始的预训练参数。
- 引入的额外参数可以通过一个轻量级的模块，即AdaptMLP，来实现，它可以并行地与原始的ViT模型中的前馈网络（FFN）相连，产生适应于目标任务的特征表示。
- AdaptMLP可以插入到不同的变换器模型中，并适用于多种视觉任务。

这些假设是否合理、局限或过于简化，需要根据实验结果和分析来判断。文章在五个图像和视频数据集上进行了广泛的实验，表明AdaptFormer在目标领域中大幅提高了ViT的性能，同时也与其他参数高效的微调方法进行了比较，并分析了AdaptFormer的优势和局限性。文章也进行了一些消融实验，探索了不同的实验配置对AdaptFormer的影响。因此，我们认为这些假设是基于合理的理论和实践基础的，但也有一些局限性和简化，例如：

- 文章只在识别任务中应用了AdaptFormer，没有探索它在其他任务，如目标检测或语义分割中的效果。
- 文章没有与其他基于变换器的模型进行比较，如DeiT [79]，Swin Transformer [83]，T2T-ViT [90]等，只使用了原始的ViT [31]作为基线。
- 文章没有分析AdaptFormer对不同数据集和任务的适应性，是否需要调整中间维度或缩放因子等超参数。
- 文章没有考虑AdaptFormer对不同预训练方法的影响，如监督预训练，自监督预训练，多模态预训练等。

# 6. 基于这篇论文的可能应用有哪些？

- **视觉变换器的高效适应**：AdaptFormer可以高效地将预训练的视觉变换器（ViT）模型适应于多种图像和视频识别任务，而无需更新原始的预训练参数。这可以节省大量的计算资源和存储空间，提高模型的通用性和可扩展性。
- **视觉识别的通用模型**：AdaptFormer可以构建一个灵活而通用的变换器模型，可以通过插入轻量级的模块来适应不同的视觉任务和领域。这可以减少任务特定的模型设计和训练，实现跨领域的知识迁移和泛化。
- **视觉变换器的新颖应用**：AdaptFormer可以探索更多基于变换器的模型在计算机视觉领域的新颖应用，如目标检测、语义分割、图像生成、视频编辑等。这可以利用变换器在建模长距离关系和多模态信息方面的优势，创造更多有趣和有用的视觉效果。

# 7. 在该文基础上，有些工作可以继续延伸下去？如何延伸？


- **探索AdaptFormer在其他视觉任务中的效果**：文章只在识别任务中应用了AdaptFormer，没有探索它在其他任务，如目标检测或语义分割中的效果。可以尝试将AdaptFormer应用于这些任务，并比较它与其他微调方法的性能和效率。
- **比较AdaptFormer与其他基于变换器的模型**：文章没有与其他基于变换器的模型进行比较，如DeiT [79]，Swin Transformer [83]，T2T-ViT [90]等，只使用了原始的ViT [31]作为基线。可以评估AdaptFormer是否可以提高这些模型的适应性和泛化性，并分析它们之间的差异和优势。
- **分析AdaptFormer对不同数据集和任务的适应性**：文章没有分析AdaptFormer对不同数据集和任务的适应性，是否需要调整中间维度或缩放因子等超参数。可以进行更多的消融实验，探索不同的超参数设置对AdaptFormer的影响，并给出一些指导和建议。
- **考虑AdaptFormer对不同预训练方法的影响**：文章没有考虑AdaptFormer对不同预训练方法的影响，如监督预训练，自监督预训练，多模态预训练等。可以使用不同的预训练方法来初始化视觉变换器模型，并观察AdaptFormer在不同领域中的表现和变化。

# 8. 这篇论文中，哪些是你还没明白的地方？
- **AdaptMLP的理论基础和优化方法**：文章没有详细解释AdaptMLP的设计动机和原理，也没有给出AdaptMLP的优化目标和算法。我不清楚AdaptMLP是如何学习到适应于目标任务的特征表示的，以及它是如何避免灾难性干扰的。
- **AdaptFormer的泛化能力和鲁棒性**：文章没有评估AdaptFormer在不同数据分布和噪声条件下的表现，也没有与其他基于变换器的模型进行泛化能力和鲁棒性的比较。我不知道AdaptFormer是否可以适应不同的数据质量和复杂度，以及它是否对一些对抗攻击或扰动有抵抗力。
- **AdaptFormer的可解释性和可视化**：文章没有提供AdaptFormer的可解释性和可视化分析，也没有探讨AdaptFormer对不同层次和位置的特征表示的影响。我不知道AdaptFormer是如何改变原始预训练模型的内部状态和输出的，以及它是如何与原始模型中的其他组件协同工作的。

# 9. 还有什么其他相关的论文？它们之间有什么关系？

# 10. 基于这篇论文的思想，若要做一个项目，能否用两句话描述一下这个项目的大致思想？

- 这个项目的目标是开发一个通用的视觉变换器模型，可以高效地适应多种图像和视频识别任务，而无需更新原始的预训练参数。
- 这个项目的方法是引入一个轻量级的模块，即AdaptMLP，可以并行地与原始的视觉变换器模型中的前馈网络相连，产生适应于目标任务的特征表示。

# 疑难解答
## 什么是ViT模型?
ViT模型是一种视觉变换器模型，它是由Google团队于2020年提出的，旨在将变换器应用于图像分类。它的模型结构简单，效果好，可扩展性强（模型越大效果越好），成为了变换器在计算机视觉领域应用的里程碑著作，也引发了后续相关研究。ViT模型的核心流程包括图像分块处理、图像块嵌入与位置编码、Transformer编码器和MLP分类处理等4个主要部分。它在ImageNet1K上的最佳模型能够达到88.55%的准确率。这说明了Transformer在计算机视觉领域确实是有效的，而且效果还挺惊人。


## 如何训练一个ViT模型?

1. 准备数据集：您需要准备一个图像分类数据集，其中包含训练和验证数据。您可以使用现有的数据集，例如ImageNet，或者使用自己的数据集。数据集应该按照类别分组，并且每个类别应该有足够的图像来训练模型。

2. 选择一个预训练的ViT模型：您可以从现有的预训练模型中选择一个作为起点。例如，您可以使用Timm库来导入预训练的ViT模型。

3. 修改模型：您需要修改模型的最后一层分类层，使其符合您的数据集中的类别数。例如，如果您使用CIFAR-10数据集，则需要将分类层更改为10个类别。

4. 训练模型：您需要定义一个损失函数和优化器，并使用训练数据来训练模型。您可以使用标准的监督学习方法来训练模型，例如交叉熵损失和随机梯度下降优化器。

5. 验证模型：在训练过程中，您需要定期使用验证数据来评估模型的性能。这可以帮助您确定模型是否过拟合或欠拟合，并调整超参数以改善性能。

6. 微调模型：如果您发现模型在验证数据上的性能不佳，您可以对模型进行微调。这包括更改学习率、增加正则化、更改数据增强方法等。


## AdaptFormer如何提高ViT模型的性能?
AdaptFormer通过引入一个轻量级的模块，即AdaptMLP，来提高ViT模型的性能。AdaptMLP可以并行地与原始的ViT模型中的前馈网络（FFN）相连，产生适应于目标任务的特征表示。它通过在保留原始预训练参数的同时，引入少量额外参数来适应目标任务。这些额外参数可以在微调阶段进行更新，以提高模型在目标领域中的性能。

在五个图像和视频数据集上进行的广泛实验表明，AdaptFormer在目标领域中大幅提高了ViT的性能。例如，在只更新1.5%额外参数的情况下，它分别在Something-Something v2和HMDB51上相对于完全微调模型提高了约10%和19%的准确率。这说明了AdaptFormer是一种有效且高效的方法，可以帮助我们更好地利用预训练的ViT模型来解决多种视觉任务。