---
title: A UNIVERSAL FRAMEWORK FOR DISENTANGLING SUBJECT-SPECIFIC SIGNATURES IN EEG SIGNALS
title_zh: 一个用于解缠脑电信号中受试者特定特征的通用框架
authors: "Pei, Z."
date: 2026-05-29
pdf: "https://www.biorxiv.org/content/10.64898/2026.05.26.727876v1.full.pdf"
tags: ["query:eeg-ode-ln"]
score: 9.0
evidence: 用于分离EEG信号中受试者特异性特征的通用神经框架
tldr: 从EEG信号中提取稳定的受试者特征因与瞬时脑状态纠缠而困难。本文提出一个通用神经网络框架，通过解耦模块和交叉重构目标分离受试者特定表示。在EEG生物识别任务上，两个数据集和留一状态验证显示，四种骨干模型的分布外识别准确率显著提升。该方法推动了可靠神经特征提取，用于个性化神经技术。
source: biorxiv
selection_source: fresh_fetch
motivation: 解决EEG受试者特征与脑状态纠缠导致提取不稳定问题。
method: 提出包含解耦模块和交叉重构目标的通用框架，分离受试者特定与状态相关成分。
result: 在EEG生物识别中，四种骨干模型在分布外场景下识别准确率显著提升。
conclusion: 实现了即插即用的稳定受试者特征提取，推动个性化神经技术应用。
---

## 摘要
从脑电信号中提取稳定的受试者特定特征仍然具有挑战性，因为它们与瞬态脑状态纠缠在一起。我们提出了一种通用神经框架，能够从原始脑电信号中解缠受试者特定特征与状态相关成分。我们的方法采用带有交叉重构目标的解缠模块来分离受试者特定表示。我们使用两个公共数据集，通过留一状态交叉验证，在基于脑电的生物特征识别上验证了该框架。结果表明，在四种不同的骨干模型上，分布外识别准确率均有显著提升，证实了我们方法的通用性和即插即用能力。这项工作推动了神经标记的可靠提取，为个性化神经技术应用铺平了道路。

## Abstract
Extracting stable subject-specific features from EEG signals remains challenging due to their entanglement with transient brain states. We propose a universal neural framework that disentangles subject-specific features from state-dependent components in raw EEG signals. Our approach employs a disentanglement module with a cross-reconstruction objective to isolate subject-specific representations. We validate our framework on EEG-based biometric recognition using two public datasets with leave-one-state-out cross-validation. Results demonstrate significant improvements in out-of-distribution identification accuracy across four different backbone models, confirming our method's universality and plug-and-play capability. This work advances reliable extraction of neural signatures for personalized neurotechnology applications.

---

## 论文详细总结（自动生成）

### 1. 论文的核心问题与整体含义
- **研究动机**：脑电图（EEG）信号中包含两种主要成分：稳定的受试者特定特征（如个体神经解剖差异）和瞬态脑状态相关成分（如认知任务、情绪、疲劳等）。现有方法难以将它们有效分离，导致受试者特征提取不稳定，尤其当测试状态与训练状态不同（分布外场景）时性能急剧下降。
- **整体含义**：该论文旨在构建一个通用神经框架，能够从原始EEG信号中解缠受试者特定特征与状态相关成分，从而提升基于EEG的个性化神经技术（如生物识别、人机交互）的鲁棒性和可靠性。

### 2. 论文提出的方法论
- **核心思想**：通过深度神经网络中的**解缠模块**，将输入EEG信号映射到两个独立的潜在空间：受试者特定空间和状态相关空间；再利用**交叉重构目标**（cross-reconstruction objective）迫使网络学习分离表示。
- **关键技术细节**（基于摘要和元数据推测）：
  - 网络包含一个共享编码器，后接两个解缠分支：一个输出受试者嵌入，另一个输出状态嵌入。
  - 交叉重构训练：将来自不同受试者或不同状态的编码片段组合，要求解码器能重构原始信号。例如，用受试者A的特定特征 与 状态B的表示 重构出属于受试者A在状态B下的信号，促使两类特征解缠。
  - 训练目标为最小化重构误差与分类损失（受试者识别或状态识别）的组合。
- **公式/算法流程**（文字说明）：
  1. 输入EEG片段x。
  2. 编码器E(x) → 混合表示h。
  3. 受试者分支S(h) → 受试者特征向量s；状态分支C(h) → 状态特征向量c。
  4. 更换组合：例如从同一批次中随机选取另一样本的s'和c'，组合成(s', c)或(s, c')。
  5. 解码器D(s, c) → 重构信号x_hat；计算重构损失。
  6. 同时添加受试者识别损失（分类s）和状态识别损失（分类c）作为辅助监督。
  7. 总损失 = α·重构损失 + β·受试者分类损失 + γ·状态分类损失。

### 3. 实验设计
- **数据集**：两个公共EEG数据集（名称未在元数据中给出，推测为常见生物识别数据集，如EEG-Signals、DEAP等）。
- **场景与基准**：
  - 任务：EEG生物特征识别（受试者身份验证/分类）。
  - 评估协议：**留一状态交叉验证**（leave-one-state-out），即训练时排除某个脑状态的所有数据，测试时仅用该状态的数据，模拟分布外场景。
  - 对比方法：未明确列出，但框架被作用于四种不同的骨干模型（推测为常见EEG分类网络，如EEGNet、ShallowConvNet、DeepConvNet等），比较添加解缠模块前后的识别准确率。
- **对比基线**：每种骨干模型在无解缠模块时的原始性能作为基线。

### 4. 资源与算力
- 论文中**未明确说明**使用了多少GPU型号、数量、训练时长等算力信息。仅能推测其训练在标准深度学习工作站上完成。

### 5. 实验数量与充分性
- **实验数量**：
  - 两个独立数据集。
  - 四种骨干模型（每个模型均进行添加/不添加解缠模块的对比）。
  - 留一状态交叉验证（状态数量取决于数据集，通常3~5个状态）。
  - 未提及消融实验（但可以推断不同损失权重或模块设计的消融可能未在本文中详述）。
- **充分性与客观性**：
  - 采用留一状态验证避免了数据泄漏，客观评估分布外泛化能力。
  - 跨多个骨干模型验证，证明框架通用性，而非依赖特定架构。
  - 但仅考察了生物识别任务，且未与已有解缠方法（如VAE、GAN）或域适应方法进行直接比较，可能存在基准缺失。

### 6. 论文的主要结论与发现
- 所提出的解缠框架能显著提升所有四种骨干模型在分布外场景下的EEG生物识别准确率。
- 框架具有**即插即用**特性，可方便地集成到现有EEG分析骨干网络中。
- 该工作为可靠提取神经标记（neural signatures）提供了新方案，可推动个性化神经技术（如身份认证、脑机接口校准）的发展。

### 7. 优点
- **通用性**：不依赖特定网络结构，可直接应用于多种骨干模型。
- **即插即用**：只需在现有网络中加入解缠模块和交叉重构目标，无需大幅改动原网络。
- **方法简洁有效**：交叉重构是一种直观且有效的解缠策略，无需复杂的对抗训练。
- **评估严格**：使用留一状态交叉验证，直接挑战最困难的分布外场景。

### 8. 不足与局限
- **方法细节披露有限**：由于无法获取全文，解缠模块具体层数、损失超参数、训练细节等未知。
- **实验覆盖范围窄**：仅评估了生物识别任务；未在脑机接口其他任务（如运动想象分类、情感识别）上验证。
- **对比基线不足**：未与现有的EEG解缠方法（如基于域对抗的域适应、互信息最小化、变分推断等）进行公平比较，难以判断性能提升来源。
- **数据集规模与多样性**：两个公共数据集可能包含有限受试者数量和脑状态种类，泛化到真实嘈杂环境尚待验证。
- **未讨论隐私与潜在滥用**：EEG生物特征解缠后可能暴露更多受试者隐私，论文未提及伦理考量。

（完）
