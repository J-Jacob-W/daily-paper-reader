---
title: "Beyond Ground Truth in K-Complex Detection: A Waveform-Based SVM Classifier and the Limits of Expert Agreement"
title_zh: 超越K-复合波检测中的真实标注：基于波形的SVM分类器与专家一致性局限性
authors: "Vazquez Chenlo, A. A., Gonzalez, M. C., Gorosito, L., Forcato, C., Ramele, R."
date: 2026-06-01
pdf: "https://www.biorxiv.org/content/10.64898/2026.05.28.728493v1.full.pdf"
tags: ["query:eeg-ode-ln"]
score: 6.0
evidence: 使用SVM对原始波形进行EEG K-复合波检测，属于EEG信号解码方法
tldr: "K-complex检测受限于专家间标注不一致和传统方法丢失时序信息。本文提出两阶段检测器：规则定位候选后，用SVM直接分类原始2秒波形。在10名受试者数据集上，SVM的F1达79.4%，超越两位专家（最佳76.2%），且假阳性中73%来自专家拒绝但具典型形态的事件。该结果质疑K-complex存在明确金标准，为睡眠分期和记忆巩固研究提供数据驱动的定义新视角。"
source: biorxiv
selection_source: fresh_fetch
motivation: 克服K-complex检测中专家标注不一致和传统特征方法丢失时序信息的局限。
method: 结合规则候选定位与直接作用于2秒原始波形的SVM分类器的两阶段检测。
result: "SVM的F1达79.4%，准确率78.8%；假阳性中73%为专家遗漏但具典型K-complex形态的事件。"
conclusion: 波形分类器匹敌专家表现，揭示视觉评分界限的模糊性，挑战K-complex检测金标准的存在。
---

## 摘要
目的K-复合波（KCs）是大振幅脑电图事件，代表N2睡眠阶段，与感觉门控、睡眠保护和记忆巩固相关。其检测受限于视觉评分中的评分者间变异性以及依赖丢弃时间信息的特征的检测器。我们提出一个两阶段检测器，结合基于规则的候选定位算法和直接对原始2秒波形操作的支持向量机（SVM）分类器，并在两个不同数据集的裁决专家共识上进行评估。

方法10名健康成年人（数据集1）的多导睡眠图记录由两名人类评分者独立标注；不一致的事件由资深专家裁决，得到240个共识KCs。自动分类器使用受试者级别的10折组K折交叉验证进行评估，并在相同条件下直接与两名人类评分者比较。进一步在公共DREAMS数据库（数据集2）上评估跨数据集泛化能力，采用外部和内部训练标准。

结果SVM分类器在所有评分者中实现了最高的F1分数（79.4%）和准确率（78.8%），具有平衡的召回率（81.7%）和特异性（75.8%）。在58个假阳性中，42个来自两位专家均拒绝的事件，但这些事件显示典型的KC形态并具有高分类器置信度（45.2%的案例中P(KC)>0.7）。该模式在数据集2上得到复现。

结论基于波形的分类器匹配专家表现，并系统性地标记出超出常规视觉评分标准的形态学有效KCs。

意义这些发现质疑了KC检测中存在明确真实标注的说法，并支持数据驱动的事件边界重新定义，对睡眠分期和记忆巩固研究具有意义。

## Abstract
ObjectiveK-complexes (KCs) are large-amplitude EEG events that represent N2 sleep stage and have been linked to sensory gating, sleep protection, and memory consolidation. Their detection remains limited by inter-rater variability in visual scoring and by the reliance of detectors on features that discard temporal information. We propose a two-stage detector that combines a rule-based candidate localization algorithm with a Support Vector Machine (SVM) classifier operating directly on the raw 2-seconds waveform, and we evaluate it against an adjudicated expert consensus of two different datasets.

MethodsPolysomnographic recordings from 10 healthy adults (Dataset 1) were independently annotated by two human scorers; discordant events were adjudicated by a senior expert, yielding 240 consensus KCs. The automatic classifier was evaluated using subject-level 10-fold Group K-Fold cross-validation and compared directly against the two human scorers under identical conditions. Cross-dataset generalization was further assessed on the public DREAMS database (Dataset 2) under both external and internal training criteria.

ResultsThe SVM classifier achieved the highest F1-score (79.4%) and accuracy (78.8%) among all scorers, with balanced recall (81.7%) and specificity (75.8%). Of the 58 false positives, 42 originated from events both experts had rejected yet displayed canonical KC morphology and received high classifier confidence (P(KC)>0.7 in 45.2% of cases). This pattern was replicated on Dataset 2.

ConclusionA waveform-based classifier matches expert performance and systematically flags morphologically valid KCs that fall outside conventional visual-scoring criteria.

SignificanceThese findings question the existence of an unambiguous ground truth for KC detection and support a data-driven redefinition of the event boundary, with implications for sleep staging and memory-consolidation research.