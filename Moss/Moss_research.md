## Moss模型调研

### 概述

MOSS是一个开源的插件增强型对话语言模型系列，具有160亿个参数。该系列模型包括了不同版本的基础模型、经过监督微调的模型以及使用插件的模型。它可以在单个A100 GPU或2个NVIDIA 3090 GPU上使用FP16精度进行推理，也可以在单个NVIDIA 3090 GPU上使用INT-4/8精度进行推理。MOSS的基础语言模型在预训练阶段使用了约7000亿个英文、中文和代码标记，并包括了PILE、BigQuery、BigPython和私有中文语料库。基础模型经过插件增强的多轮对话数据上进行微调，并进行了偏好感知训练以进一步提升模型性能。

### 模型列表

1. moss-moon-003-base：
   - MOSS-003的基础语言模型。
   - 使用CodeGen初始化，进一步在1000亿中文标记和200亿英文标记上进行预训练。
   - 总共预训练了7000亿标记，消耗了约6.67x1022 FLOPs的计算力。
2. moss-moon-003-sft：
   - 在约110万条多轮对话数据上进行了监督微调。
   - 经过微调后的模型可以遵循多轮对话中的指令，并拒绝不适当的请求。
3. moss-moon-003-sft-plugin：
   - 在约110万条多轮对话数据和额外的约30万条插件增强数据上进行了监督微调。
   - 经过微调后，该模型能够使用多种工具，包括搜索引擎、文本到图像工具、计算器和方程式求解器。
4. moss-moon-003-sft-int4：
   - moss-moon-003-sft的4位版本，需要12GB GPU内存进行推理。
5. moss-moon-003-sft-int8：
   - moss-moon-003-sft的8位版本，需要24GB GPU内存进行推理。
6. moss-moon-003-sft-plugin-int4：
   - moss-moon-003-sft-plugin的4位版本，需要12GB GPU内存进行推理。
7. moss-moon-003-sft-plugin-int8：
   - moss-moon-003-sft-plugin的8位版本，需要24GB GPU内存进行推理。
8. moss-moon-003-pm：
   - 使用moss-moon-003-sft的回答数据训练的偏好模型（PM）。
   - 该模型将在不久的将来开源。
9. moss-moon-003：
   - 使用moss-moon-003-pm训练的最终版本MOSS-003模型。
   - 表现出更好的事实准确性、安全性和响应质量。
   - 该模型将在不久的将来开源。
10. moss-moon-003-plugin：
    - 使用moss-moon-003-pm训练的最终版本MOSS-003-plugin模型。
    - 具有更强的理解用户意图和使用插件的能力。
    - 该模型将在不久的将来开源。



### 数据集说明

- moss-002-sft-data数据集是用于训练MOSS-002的多轮对话数据，包括570,000条英文对话和590,000条中文对话。这些数据由text-davinci-003生成，涵盖了有益性、诚实性和无害性。

- moss-003-sft-data数据集是用于训练moss-moon-003-sft的多轮对话数据。这些数据是通过gpt-3.5-turbo从一组用户提示中生成的，这些用户提示是通过早期部署的MOSS-002 API收集的。与moss-002-sft-data相比，moss-003-sft-data更好地与真实用户意图的分布保持一致，涵盖了更细粒度的类别和更多样化的与无害性相关的数据。该数据集总共包括约1,100,000条对话。目前已经开源了其中一小部分数据，并将在不久的将来公开完整数据。

- moss-003-sft-plugin-data数据集是插件增强的多轮对话数据，其中AI助手使用了四个插件（搜索引擎、文本到图像、计算器和方程式求解器）来生成回复。该数据集包含约30万条对话。目前已经开源了其中一小部分数据，并将在不久的将来公开完整数据。

- moss-003-pm-data数据集是用于训练moss-moon-003-pm的偏好数据，包括约18万个对话上下文及其相应的回复，这些数据是由moss-moon-003-sft生成的。该数据将在不久的将来对公众开放。







### 工程解决方案

1. MOSS Vortex：MOSS模型推理和部署的解决方案。
2. MOSS WebSearchTool：MOSS-003使用的网络搜索插件的解决方案。
3. MOSS Frontend：基于Flutter的MOSS-003前端界面。
4. MOSS Backend：基于Go的MOSS-003后端。

### 限制

由于参数数量相对较少和自回归的特性，MOSS仍有可能生成包含错误、误导或偏颇信息的输出。在使用MOSS生成的内容之前，请仔细检查其准确性。







### 总结

MOSS-003模型系列通过基础模型、监督微调和插件等方式，实现了强大的对话能力和多样化的功能。这些模型在事实准确性、安全性和响应质量方面表现出色，并具备执行各种任务的能力。MOSS-003系列模型的开源将进一步促进对话系统领域的发展和应用。