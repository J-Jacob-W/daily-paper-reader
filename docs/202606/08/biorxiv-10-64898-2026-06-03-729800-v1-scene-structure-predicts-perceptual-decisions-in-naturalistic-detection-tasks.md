---
title: Scene Structure Predicts Perceptual Decisions in Naturalistic Detection Tasks
title_zh: 场景结构预测自然场景检测任务中的感知决策
authors: "Yang, J., Vercillo, T., Cutrona, T. E., Azeglio, S., Iannetti, G., Neri, P."
date: 2026-06-08
pdf: "https://www.biorxiv.org/content/10.64898/2026.06.03.729800v1.full.pdf"
tags: ["query:eeg-ode-ln"]
score: 7.0
evidence: 结合EEG和深度神经网络研究自然场景中的感知决策
tldr: 自然场景中物体检测机制尚不完全清楚。本研究结合心理物理学、户外增强现实、深度神经网络、图像特征分析和脑电图，发现背景统计结构系统性地影响近阈值刺激的感知决策。深度神经网络可基于背景图像预测行为正确与否，纹理熵和边缘密度是关键信息特征。脑电图在无探针前图像窗口即区分了正确与错误试次。该工作为理解环境结构与神经动态如何共同支持感知决策提供了统一框架。
source: biorxiv
selection_source: fresh_fetch
motivation: 自然场景中物体感知机制尚未阐明，尤其是背景上下文如何影响近阈值检测任务中的感知决策。
method: 结合心理物理学实验、户外AR、深度神经网络、图像低层统计特征分析和EEG，系统研究背景结构对感知决策的影响。
result: 背景统计结构系统性影响行为表现；DNN预测正确/错误；纹理熵和边缘密度是关键特征；EEG在刺激前窗口区分后续决策。
conclusion: 感知决策不仅取决于目标，还受周围场景统计结构塑造，环境结构与神经动态共同支持感知决策。
---

## 摘要
人类视觉系统能够识别复杂自然场景中的物体，但在这种多变条件下支持稳健感知的机制仍不完全清楚。本文研究自然场景的统计结构如何塑造感知证据形成，并决定近阈值刺激是否正确或错误地被感知。我们结合控制心理物理学、户外增强现实（AR）、深度神经网络（DNN）、图像特征分析和脑电图（EEG），考察背景上下文如何调节感知决策。在多个检测任务中，人类表现受到无探针背景结构的系统性影响。仅基于背景图像训练的DNN预测了正确和错误的行为结果，在后提示条件下效果更强，表明当空间不确定性较高时，全局场景上下文有助于局部感知决策。AR实验进一步表明，这些上下文驱动效应在自然观看环境中持续存在。为识别这些效应背后的视觉信息，我们分析了低级图像统计量。纹理熵和边缘密度成为信息性特征，基于这些指标的传统机器学习模型实现了有意义的正确/错误分类。最后，EEG分析揭示了图像驱动感知变异性的神经信号：无探针预图像窗口期间的活动区分了后来的正确与错误试验，而将EEG与图像衍生特征结合提高了解码性能。这些发现共同表明，自然场景中的感知并非仅由目标决定，而是受到周围上下文的统计结构塑造。通过将心理物理学、AR、DNN建模、图像统计和EEG联系起来，这项工作为理解环境结构和神经动力学如何共同支持感知决策提供了一个统一框架。

## Abstract
The human visual system can identify objects in complex natural scenes, yet the mechanisms supporting robust perception under such variable conditions remain incompletely understood. Here, we investigate how the statistical structure of natural scenes shapes perceptual evidence formation and determines whether near-threshold stimuli are perceived correctly or incorrectly. We combine controlled psychophysics, outdoor augmented reality (AR), deep neural networks (DNNs), image-feature analysis, and EEG to examine how background context modulates perceptual decisions. Across multiple detection tasks, human performance was systematically influenced by probe-free background structure. DNNs trained on background images alone predicted correct and incorrect behavioral outcomes, with stronger effects in postcue conditions, suggesting that global scene context contributes to local perceptual decisions when spatial uncertainty is higher. AR experiments further showed that these context-driven effects persist in naturalistic viewing environments. To identify the visual information underlying these effects, we analyzed low-level image statistics. Texture entropy and edge density emerged as informative features, and conventional machine-learning models trained on these measures achieved meaningful correct/incorrect classification. Finally, EEG analyses revealed neural signatures of image-driven perceptual variability: activity during the probe-free preimage window distinguished later correct from incorrect trials, and combining EEG with image-derived features improved decoding performance. Together, these findings show that perception in natural scenes is not determined solely by the target, but is shaped by the statistical structure of the surrounding context. By linking psychophysics, AR, DNN modeling, image statistics, and EEG, this work provides a unified framework for understanding how environmental structure and neural dynamics jointly support perceptual decision-making.