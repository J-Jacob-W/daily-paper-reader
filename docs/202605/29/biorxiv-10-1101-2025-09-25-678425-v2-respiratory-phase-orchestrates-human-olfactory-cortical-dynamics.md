---
title: Respiratory Phase Orchestrates Human Olfactory Cortical Dynamics
title_zh: 呼吸相位组织人类嗅觉皮层动态
authors: "Hathaway, A. Y., Coleman, T. P."
date: 2026-05-27
pdf: "https://www.biorxiv.org/content/10.1101/2025.09.25.678425v2.full.pdf"
tags: ["query:eeg-ode-ln"]
score: 8.0
evidence: 使用EEG解码呼吸相位锁定的嗅觉皮层动态
tldr: "传统嗅觉神经研究忽略呼吸相位变异性，难以捕捉自然嗅闻下的皮层动态。本研究通过同步呼吸与EEG记录，在自然呼吸周期中呈现气味，采用呼吸相位锁定的事件相关谱扰动（RPL-ERSPs）分析。结果发现，RPL-ERSPs在theta（吸气）和alpha（呼气）频带有效区分气味（peppermint AUC=0.78, oregano AUC=0.68, grapefruit AUC=0.61），跨个体泛化且与行为识别一致。该工作揭示呼吸节律是嗅觉皮层处理的时间支架，提供低成本开源装置，RPL-ERSPs可作为无任务嗅觉评估的敏感指标。"
source: biorxiv
selection_source: fresh_fetch
motivation: 传统时间锁定分析忽略呼吸相位变异性，无法揭示自然嗅闻下的嗅觉皮层动态。
method: 同步呼吸与EEG，在自然呼吸周期中呈现气味，提取呼吸相位锁定的事件相关谱扰动（RPL-ERSPs）。
result: RPL-ERSPs在theta（吸气）和alpha（呼气）频带区分气味，跨个体泛化（AUC 0.61-0.78），行为识别与神经解码一致。
conclusion: 呼吸节律组织嗅觉皮层活动，RPL-ERSPs可作为无任务嗅觉评估的敏感指标。
---

## 摘要
嗅觉是感知、记忆和情感的基础，然而人类气味加工的神经基础仍知之甚少。在此，我们证明气味诱发的脑活动是由呼吸相位——而非绝对时间——组织的，揭示了自然呼吸构建了嗅觉皮层动态。通过同时记录17名参与者的鼻腔呼吸和脑电图，我们递送了与个体呼吸周期同步的自然气味（薄荷、牛至和葡萄柚）。气味呈现诱发了额叶和颞叶区域独特的、呼吸相位锁定的事件相关频谱扰动，这些扰动在刺激开始后的第一次呼吸期间出现。最具区分度的神经特征是吸气期间的θ波段活动和呼气期间的α波段活动，这些模式由于呼吸持续时间的自然变异而在传统时间锁定分析中被掩盖。基于留一法交叉验证的RPL-ERSPs实现了可靠的气味区分（薄荷：AUC = 0.78；牛至：AUC = 0.68；葡萄柚：AUC = 0.61），确立了相位锁定特征可跨个体泛化。为了在不依赖精确气味命名（这众所周知困难，且在某些人群中可能不成比例地受损）的情况下将神经反应与知觉体验联系起来，我们使用自由反应描述并通过语义相似性方法评分来量化气味识别。行为识别强度与跨气味的神经解码层次相对应，确立了RPL-ERSPs的知觉有效性。RPL-ERSPs还揭示了快速习惯化，由于最具信息量的相位锁定特征的选择性退化，解码性能在重复呈现后下降。总之，这些发现确立了呼吸节律作为人类嗅觉皮层加工的时间支架，将RPL-ERSPs定位为一种灵敏、无需任务的方法来评估嗅觉功能。我们提供开源的呼吸同步嗅觉计设计（<500美元），以促进该方法的复制和更广泛应用。

## Abstract
Olfaction is fundamental to perception, memory, and emotion, yet the neural basis of human odor processing remains poorly understood. Here, we demonstrate that odor-evoked brain activity is organized by respiratory phase--not absolute time--revealing that natural breathing structures olfactory cortical dynamics. Using simultaneous nasal respiration and electroencephalography (EEG) recordings in 17 participants, we delivered naturalistic odors (peppermint, oregano, and grapefruit) synchronized to individual breathing cycles. Odor presentation elicited distinct, respiratory phase-locked event-related spectral perturbations (RPL-ERSPs) in frontal and temporal regions, emerging during the first breath after stimulus onset. The most discriminative neural signatures were theta-band activity during inhalation and alpha-band activity during exhalation, patterns that were obscured in traditional time-locked analyses due to natural variability in breath duration. Leave-one-subject-out cross-validation of RPL-ERSPs achieved reliable odor discrimination (peppermint: AUC = 0.78; oregano: AUC = 0.68; grapefruit: AUC = 0.61), establishing that phase-locked features generalize across individuals. To connect neural responses to perceptual experience without relying on precise odor naming--which is notoriously difficult and can be disproportionately impaired in some populations--we quantified odor recognition using free-response descriptions scored with a semantic-similarity approach. Behavioral recognition strength paralleled the neural decoding hierarchy across odors, establishing the perceptual validity of RPL-ERSPs. RPL-ERSPs also revealed rapid habituation, with decoding performance declining over repeated presentations, due to selective degradation of the most informative phase-locked features. Together, these findings establish respiratory rhythm as a temporal scaffold for human olfactory cortical processing, positioning RPL-ERSPs as a sensitive, task-free approach for assessing olfactory function. We provide an open-source, respiration-synchronized olfactometer design (<$500) to enable replication and broader adoption of this approach.