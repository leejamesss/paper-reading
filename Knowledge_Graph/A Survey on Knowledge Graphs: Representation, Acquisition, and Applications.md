

# A Survey on Knowledge Graphs: Representation, Acquisition, and Applications

这篇文章是一篇关于知识图谱的综述，介绍了知识图谱的表示、获取和应用方面的研究进展和挑战。知识图谱是一种结构化的人类知识的表示，包含了实体、关系和语义描述。知识图谱可以用于认知和人工智能领域，提高信息检索、自然语言理解、推荐系统等应用的效果。文章从四个方面对知识图谱进行了分类和分析，分别是知识图谱表示学习、知识获取、时序知识图谱和知识感知应用，并总结了一些未来的研究方向。

![image](https://github.com/leejamesss/paper-reading/assets/117844938/3431c5ce-f5fb-4d51-8540-2108b8ef989c)


## 要点

-   知识图谱是一种结构化的人类知识的表示，包含了实体、关系和语义描述。
-   知识图谱可以用于认知和人工智能领域，提高信息检索、自然语言理解、推荐系统等应用的效果。
-   文章从四个方面对知识图谱进行了分类和分析，分别是知识图谱表示学习、知识获取、时序知识图谱和知识感知应用，并总结了一些未来的研究方向。
-   文章介绍了不同的知识图谱表示空间、评分函数、编码模型和辅助信息，并比较了它们的优缺点和表达能力。
-   文章还讨论了一些新兴的主题，如变换器模型、图神经网络、强化学习、元关系学习等在知识图谱上的应用。

### 知识图谱表示学习、知识获取、时序知识图谱和知识感知应用

- 知识图谱表示学习是指将知识图谱中的实体和关系映射到低维向量空间，同时保留它们的语义信息。知识图谱表示学习的目的是为了方便后续的知识推理和应用。知识图谱表示学习可以从不同的角度进行分类，例如表示空间、评分函数、编码模型和辅助信息。

- 知识获取是指从不同的数据源中抽取、整合和补全知识图谱中的实体、关系和事实。知识获取的目的是为了扩充和完善知识图谱，提高其覆盖率和质量。知识获取可以分为三个子任务，即知识图谱补全、关系抽取和实体发现。

- 时序知识图谱是指在知识图谱中加入时间信息，以表达实体和关系随时间变化的动态性。时序知识图谱的目的是为了捕捉知识图谱中的时序规律和因果关系，提高其预测能力和可解释性。时序知识图谱可以分为四个研究领域，即时序嵌入、实体动态、时序关系依赖和时序逻辑推理。

- 知识感知应用是指利用知识图谱中的结构化信息、丰富语义和多语言知识来提升不同领域的应用效果。知识感知应用的目的是为了利用知识图谱的优势，实现常识理解和推理，提高用户体验和满意度。知识感知应用可以涵盖多个领域，例如自然语言理解、问答系统、推荐系统等。


- 变换器模型是一种基于自注意力机制的神经网络模型，可以有效地处理序列数据。变换器模型在知识图谱上的应用主要有两个方面，一是用于知识图谱表示学习，二是用于知识图谱推理。例如，CoKE 是一个基于变换器的知识图谱表示学习模型，它将三元组作为序列输入，并用MASK代替一个实体，然后利用变换器编码三元组的语义信息，并预测被遮蔽的实体。K-BERT 是一个基于变换器的知识图谱推理模型，它将知识图谱中的实体和关系作为特殊的标记插入到文本中，然后利用变换器编码文本和知识的联合表示，并进行下游的自然语言理解任务。

- 图神经网络是一种能够处理图结构数据的神经网络模型，可以有效地捕捉实体和关系之间的复杂依赖关系。图神经网络在知识图谱上的应用主要有两个方面，一是用于知识图谱表示学习，二是用于知识图谱补全。例如，R-GCN 是一个基于图卷积网络的知识图谱表示学习模型，它将知识图谱作为一个有向异构图，并利用图卷积网络编码实体和关系的嵌入向量。ConvKB 是一个基于图卷积网络的知识图谱补全模型，它将三元组作为一个局部子图，并利用图卷积网络提取三元组的潜在特征，并计算三元组的可信度。

- 强化学习是一种基于奖励信号和探索策略的机器学习方法，可以有效地解决序列决策问题。强化学习在知识图谱上的应用主要是用于知识图谱推理，即通过在知识图谱中寻找合理的路径来推断缺失的事实或回答问题。例如，MINERVA是一个基于强化学习的知识图谱推理模型，它将推理过程建模为一个马尔可夫决策过程，并利用深度Q网络学习一个路径选择策略，以最大化预测正确率。ReGNN是一个基于强化学习和图神经网络的知识图谱推理模型，它将推理过程建模为一个生成式对抗网络，并利用图神经网络编码实体和关系的嵌入向量，并生成候选路径。

- 元关系学习是一种能够处理多重关系类型和多重关系角色的学习方法，可以有效地捕捉知识图谱中的复杂语义信息。元关系学习在知识图谱上的应用主要是用于知识图谱补全，即通过考虑不同关系类型和角色之间的相互作用来预测缺失的事实。例如，M-Walk 是一个基于元关系学习的知知识图谱补全模型，它将知识图谱中的实体和关系作为元关系类型和角色，并利用随机游走生成多重关系路径，并计算路径的可信度。MetaR 是一个基于元关系学习的知识图谱补全模型，它将知识图谱中的实体和关系作为元关系类型和角色，并利用元关系网络编码实体和关系的嵌入向量，并预测缺失的事实。




### 不同的知识图谱表示空间、评分函数、编码模型和辅助信息，并比较它们的优缺点和表达能力。

知识图谱表示空间是指将知识图谱中的实体和关系映射到的低维空间，不同的表示空间有不同的特点和适用范围。

-   点式空间：将实体和关系表示为实数向量、矩阵或张量，是最常用的表示空间，具有简单直观、计算高效的优点，但也存在无法捕捉复杂语义、过度约束、信息损失等缺点。例如，TransE 、TransR 、NTN 等模型都使用点式空间。
-   复数空间：将实体和关系表示为复数向量，可以有效地捕捉对称和反对称关系，具有表达能力强、计算简洁的优点，但也存在无法处理多值关系、难以解释等缺点。例如，ComplEx 、RotatE 、QuatE 等模型都使用复数空间。
-   高斯分布：将实体和关系表示为高斯分布，可以有效地处理实体和关系的不确定性，具有概率化推理、鲁棒性强的优点，但也存在计算复杂、难以优化等缺点。例如，KG2E 、TransG 等模型都使用高斯分布。
-   流形空间：将实体和关系表示为流形上的点，可以有效地捕捉层次结构和几何形态，具有表达能力强、适应性强的优点，但也存在计算复杂、难以优化等缺点。例如，ManifoldE 、MuRP 、Chami et al. 等模型都使用流形空间。

![image](https://github.com/leejamesss/paper-reading/assets/117844938/18ad4dca-bf2b-458d-b711-a59b02db2781)


知识图谱评分函数是指用于衡量三元组合理性的函数，不同的评分函数有不同的计算方式和适用范围。

-   距离型评分函数：通过计算实体之间的距离来衡量三元组合理性，通常采用加性平移原则h+r≈t，具有简单直观、计算高效的优点，但也存在无法捕捉复杂语义、过度约束、信息损失等缺点。例如，TransE 、TransH 、KG2E 等模型都使用距离型评分函数。
-   相似性评分函数：通过计算实体之间的相似性来衡量三元组合理性，通常采用乘性匹配原则，具有表达能力强、计算简洁的优点，但也存在无法处理多值关系、难以解释等缺点。例如，DistMult 、ComplEx 、HolE 等模型都使用相似性评分函数。

![image](https://github.com/leejamesss/paper-reading/assets/117844938/a7a616d6-975f-4cb0-a3c3-2b500f6e98f9)


知识图谱编码模型是指用于建模实体和关系之间的交互方式的模型，不同的编码模型有不同的结构和功能。

- 线性/双线性模型：通过线性或双线性变换来建模实体和关系之间的交互方式，具有简单直观、计算高效的优点，但也存在无法捕捉复杂语义、过度约束、信息损失等缺点。例如，SE、SME、DistMult、ComplEx、ANALOGY等模型都使用线性/双线性模型。
- 因子分解模型：通过将知识图谱张量分解为低秩矩阵来建模实体和关系之间的交互方式，具有表达能力强、计算简洁的优点，但也存在无法处理多值关系、难以解释等缺点。例如，RESCAL、TuckER、LowFER等模型都使用因子分解模型。
- 神经网络模型：通过使用非线性神经激活和更复杂的网络结构来建模实体和关系之间的交互方式，具有表达能力强、计算灵活的优点，但也存在计算复杂、难以优化等缺点。例如，MLP、NTN、NAM等模型都使用神经网络模型。
- 卷积神经网络模型：通过使用卷积操作来学习深层表达特征来建模实体和关系之间的交互方式，具有表达能力强、计算高效的优点，但也存在无法处理多值关系、难以解释等缺点。例如，ConvE、ConvKB、HypER等模型都使用卷积神经网络模型。

![image](https://github.com/leejamesss/paper-reading/assets/117844938/0fe3ace3-229e-42cf-a69d-cbfe12c3fe8a)


知识图谱辅助信息是指用于增强知识图谱表示学习的外部信息，不同的辅助信息有不同的来源和作用。

- 文本信息：利用知识图谱中实体或关系对应的文本描述或文档内容来增强知识图谱表示学习，具有丰富语义、提高泛化能力的优点，但也存在文本质量不一、难以对齐等缺点。例如，SSP、DKRL、TKRL等模型都使用文本信息作为辅助信息。
- 视觉信息：利用知识图谱中实体或关系对应的图像或视频内容来增强知识图谱表示学习，具有丰富语义、提高泛化能力的优点，但也存在视觉质量不一、难以对齐等缺点。例如，ViZDoomKG、VTransE、MMKG等模型都使用视觉信息作为辅助信息。
- 类型信息：利用知识图谱中实体或关系所属的类型或类别来增强知识图谱表示学习，具有提供约束、提高准确性的优点，但也存在类型不完整、难以扩展等缺点。例如，TransC、TransF、TransA等模型都使用类型信息作为辅助信息。
- 路径信息：利用知识图谱中实体或关系之间的路径或子图来增强知识图谱表示学习，具有提供上下文、提高可解释性的优点，但也存在路径不完整、难以搜索等缺点。例如，PTransE、R-GCN、RSN等模型都使用路径信息作为辅助信息。
- 逻辑规则信息：利用知识图谱中实体或关系之间的逻辑规则或约束来增强知识图谱表示学习，具有提供推理、提高一致性的优点，但也存在规则不完整、难以融合等缺点。例如，RUGE、DRUM、NeuralLP等模型都使用逻辑规则信息作为辅助信息。

  ![image](https://github.com/leejamesss/paper-reading/assets/117844938/b290e39f-9b84-42b6-8cf1-27d874104f71)




	
