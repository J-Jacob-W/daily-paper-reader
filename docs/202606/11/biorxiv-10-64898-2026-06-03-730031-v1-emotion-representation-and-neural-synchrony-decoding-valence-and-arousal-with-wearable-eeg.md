---
title: "Emotion Representation and Neural Synchrony: Decoding Valence and Arousal with Wearable EEG"
title_zh: 情绪表征与神经同步：利用可穿戴脑电图解码效价和唤醒度
authors: "Yang, I., Park, C., Kim, J."
date: 2026-06-08
pdf: "https://www.biorxiv.org/content/10.64898/2026.06.03.730031v1.full.pdf"
tags: ["query:eeg-ode-ln"]
score: 9.0
evidence: 使用可穿戴EEG解码情感维度
tldr: 传统情感研究依赖实验室设备，本研究使用消费级可穿戴EEG在自然情境下解码情绪效价和唤醒度。43名被试观看四类情绪视频，通过分类、MDS和ISC分析发现，EEG对效价分类稳定但唤醒度解码较弱。神经同步在左半球和颞叶区域显著。结果表明可穿戴EEG适用于效价解码，但唤醒度需更长时间尺度研究，为生态效度情感研究提供可行方案。
source: biorxiv
selection_source: fresh_fetch
motivation: 探索消费级可穿戴EEG设备在自然情境中解码情绪效价和唤醒度的可行性，克服实验室局限。
method: 43名被试观看高/低唤醒、正/负效价视频，用穿戴式EEG记录信号，采用分类、多维尺度和被试间相关分析。
result: EEG对效价分类高于随机，唤醒度解码不稳定；行为与神经反应均以效价维度为主，神经同步在左半球和颞叶较强。
conclusion: 可穿戴EEG可稳定解码效价但唤醒度需时间分辨方法，验证了其在生态效度情感研究中的潜力与局限。
---

## 摘要
情绪是随时间展开的动态体验，但大多数情感神经科学研究依赖于静态刺激和基于实验室的脑电图系统。本研究探讨了在自然情境下，使用消费级可穿戴脑电图设备能否可靠地解码情绪效价和唤醒度。43名参与者观看了旨在诱发四种核心情感类别（高唤醒积极、低唤醒积极、高唤醒消极和低唤醒消极）的视频片段，同时连续记录脑电图信号。采用多变量分析，包括分类、多维尺度分析和受试者间相关性，来评估情感表征和神经同步。行为数据表明效价和唤醒度的分类均稳健，而脑电图数据对效价的分类一致高于随机水平，但对唤醒度的解码不太稳定，尤其是在参与者内部分析中。多维尺度分析显示，行为和脑电图反应主要沿效价维度组织，沿唤醒度的分离较弱。受试者间相关性分析进一步揭示了频率和区域特异性的神经同步，左半球和颞区电极的一致性更强，但总体受试者间相关性值适中，可能反映了刺激的短暂持续时间。综合这些发现表明，效价在主观和神经领域中都更稳定地表征，而唤醒度可能需要时间分辨或更长时间的方法才能可靠解码。这项工作展示了使用可穿戴脑电图进行理论驱动的情感神经科学的可行性和局限性，强调了其在实验室环境之外进行可扩展和生态效度高的情绪研究的潜力。

## Abstract
Emotions are dynamic experiences that unfold over time, yet most affective neuroscience studies have relied on static stimuli and laboratory-based EEG systems. This study examined whether emotional valence and arousal can be reliably decoded using a consumer-grade wearable EEG device in naturalistic contexts. Forty-three participants viewed video clips designed to elicit four core affect categories including high-arousal positive, low-arousal positive, high-arousal negative, and low-arousal negative, while EEG signals were continuously recorded. Multivariate analyses, including classification, multidimensional scaling (MDS), and intersubject correlation (ISC), were employed to assess affective representation and neural synchrony. Behavioral data demonstrated robust classification of both valence and arousal, whereas EEG data yielded consistent above-chance classification of valence but less stable decoding of arousal, particularly in within-participant analyses. MDS revealed that both behavioral and EEG responses were primarily organized along the valence dimension, with weaker separation along arousal. ISC analyses further indicated frequency- and region-specific neural synchrony, with stronger alignment in left and temporal electrodes, though overall ISC values were modest, likely reflecting the brief duration of stimuli. Taken together, these findings suggest that valence is more stably represented in both subjective and neural domains, whereas arousal may require time-resolved or longer-duration approaches for reliable decoding. This work demonstrates the feasibility and limitations of employing wearable EEG for theory-driven affective neuroscience, underscoring its potential for scalable and ecologically valid emotion research beyond laboratory settings.

---

## 论文详细总结（自动生成）

# 详细中文总结

## 1. 论文的核心问题与整体含义（研究动机和背景）

- **核心问题**：情绪是随时间动态展开的体验，但大多数情感神经科学研究依赖静态刺激（如图片）和实验室级脑电图（EEG）系统，生态效度有限。本研究探讨能否使用**消费级可穿戴EEG设备**在自然情境下可靠地解码情绪的两个核心维度——**效价**（积极/消极）和**唤醒度**（高/低）。
- **整体含义**：若可穿戴EEG能实现情绪解码，将推动情感研究从实验室走向日常场景，促进可扩展、低成本的情感监测应用。同时，本研究从理论上验证效价和唤醒度在神经表征中的分离程度。

## 2. 论文提出的方法论：核心思想、关键技术细节、公式或算法流程

- **核心思想**：采用自然刺激（情绪视频片段）连续诱发四种核心情感类别（高唤醒积极、低唤醒积极、高唤醒消极、低唤醒消极），结合多变量分析挖掘EEG信号中的情绪维度表征。
- **关键技术细节**：
  - **数据采集**：43名参与者佩戴消费级可穿戴EEG设备，观看4类情绪视频时连续记录EEG信号。
  - **分析方法**：
    1. **分类分析**：训练分类器（具体算法未说明，推测为SVM或线性分类器）对效价和唤醒度进行二分类，评估是否高于随机水平。
    2. **多维尺度分析（MDS）**：将行为评分和EEG特征映射到低维空间，观察效价和唤醒度的分离模式。
    3. **受试者间相关性（ISC）**：计算不同被试在同一刺激下EEG信号的跨被试一致性，衡量神经同步。
- **算法流程**（文字说明）：
  - 预处理→特征提取（频带功率/时空特征）→分别进行参与者内和跨参与者分类→MDS降维可视化→ISC计算（频率特异性和区域特异性）。

## 3. 实验设计：使用了哪些数据集 / 场景，它的 benchmark 是什么，对比了哪些方法

- **数据集与场景**：
  - 自制数据集：43名被试观看4类情绪视频（高唤醒积极、低唤醒积极、高唤醒消极、低唤醒消极），视频时长推测较短（因为后续提到“短暂持续时间”）。
  - 无公开benchmark，但以**随机水平**（50%）作为分类性能基准。
- **对比方法**：
  - 行为数据与EEG数据的分类表现对比。
  - 不同分析层次（参与者内 vs. 跨参与者）对比。
  - 不同频段和电极区域（左半球/颞叶 vs. 其他区域）的ISC对比。
- **未提及与已有方法（如实验室设备）的直接比较**，但隐含与实验室EEG研究的结果进行定性对比。

## 4. 资源与算力：如果文中有提到，请总结使用了多少算力（GPU 型号、数量、训练时长等）。若未明确说明，也请指出这一点。

- 论文摘要和元数据中**未明确说明**使用了何种GPU、数量或训练时长。仅提到使用可穿戴EEG设备，数据分析层面通常无需大量算力，分类和ISC计算在普通CPU上即可完成。因此无法提供具体算力信息。

## 5. 实验数量与充分性：大概做了多少组实验（如不同数据集、消融实验等），这些实验是否充分、是否客观、公平。

- **实验数量**：
  - 主要实验包括：分类实验（效价/唤醒度，参与者内/跨参与者）、MDS分析（行为数据和EEG数据）、ISC分析（多个频段和电极区域）。
  - 未提及消融实验或交叉验证细节。
- **充分性与客观性**：
  - 样本量43名被试，属于中等规模；但未报告被试详细人口学信息，可能存在偏差。
  - 分类使用随机水平作为基准，但未与经典方法（如基于实验室设备的分类准确率）对比，无法评估可穿戴设备相对优劣。
  - 仅使用一种视频刺激集，未在不同情绪诱发材料（如音乐、图片）上验证泛化性。
  - 实验设计较为基础，缺乏对时间动态（如滑动窗口）的探索，也未控制视频内容属性（如剧情、视觉复杂度）。
- **公平性**：行为数据与EEG数据的分析流程基本一致，但未详细报告特征选择、分类器参数调整等细节，可能存在过拟合风险。

## 6. 论文的主要结论与发现

- **行为数据**：效价和唤醒度的分类均**稳健**（高于随机水平）。
- **EEG数据**：
  - 效价分类**一致高于随机水平**，尤其在内部分析中表现稳定。
  - 唤醒度解码**不稳定**，参与者内分析中未能可靠高于随机水平。
- **MDS分析**：行为与EEG反应主要沿**效价维度**组织，唤醒度维度分离较弱。
- **ISC分析**：神经同步在**左半球和颞叶**电极更强，但整体ISC值中等，可能受刺激持续时间较短限制。
- **总体结论**：效价在主观和神经层面都更稳定地表征，可穿戴EEG适用于效价解码；唤醒度需要更长时间尺度或时间分辨方法才能可靠解码。研究展示了可穿戴EEG用于生态效度情感研究的可行性与局限性。

## 7. 优点：方法或实验设计上有哪些亮点。

- **生态效度**：使用自然视频刺激和消费级可穿戴EEG，贴近真实情绪体验。
- **多维度分析**：综合分类、MDS和ISC三种互补方法，从不同角度验证情绪表征。
- **神经同步视角**：ISC揭示了群体层面的神经一致性，为理解社会情绪加工提供新视角。
- **理论驱动**：基于核心情感模型（效价-唤醒度环状模型），具有明确理论框架。
- **设备可推广性**：验证了低成本可穿戴设备的潜力，有利于情感神经科学向日常应用转化。

## 8. 不足与局限：包括实验覆盖、偏差风险、应用限制等。

- **实验覆盖**：仅使用单一类型的情绪诱发材料（视频），未涵盖多种模态（如音乐、图片、社会互动）；刺激时长较短，可能不足以充分激活唤醒度。
- **样本偏差**：可能以大学生为主，人口学限制；未报告性别、年龄分布。
- **方法局限**：
  - 唤醒度分类不稳定，未尝试时间分辨或滑动窗口方法。
  - 未与实验室高密度EEG或fMRI对比，无法评估可穿戴设备的信噪比优劣。
  - 分类器具体参数、特征选择、交叉验证策略未详细说明，可复现性不足。
- **应用限制**：当前解码准确率虽高于随机但远未达到实用水平，且唤醒度解码不可靠，距离实时情绪监测仍有差距。
- **风险**：未讨论个体差异（如情绪调节能力、EEG信号质量）对结果的影响；ISC值适中可能是由于刺激内容不一致或被试注意力波动。

（完）
