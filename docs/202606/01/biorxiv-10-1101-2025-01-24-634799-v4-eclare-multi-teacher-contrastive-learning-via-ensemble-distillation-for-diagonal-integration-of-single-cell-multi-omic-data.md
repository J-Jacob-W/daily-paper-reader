---
title: "ECLARE: multi-teacher contrastive learning via ensemble distillation for diagonal integration of single-cell multi-omic data"
title_zh: ECLARE：通过集成蒸馏的多教师对比学习实现单细胞多组学数据的对角整合
authors: "Mann-Krzisnik, D., Chawla, A., Turecki, G., Nagy, C., Li, Y."
date: 2026-05-27
pdf: "https://www.biorxiv.org/content/10.1101/2025.01.24.634799v4.full.pdf"
tags: ["query:multi-modal"]
score: 7.0
evidence: 多教师对比学习整合多模态单细胞数据
tldr: 单细胞多组学数据整合面临特征对齐和配对数据有限的挑战。ECLARE利用多教师集成知识蒸馏与对比学习，通过配对数据训练教师模型指导学生模型对齐未配对数据，并采用最优传输损失增强跨模态对齐。在基准测试中，该方法在细胞配对准确性、整合质量和生物结构保持方面表现优异。应用于抑郁症未配对数据，揭示了性别和细胞类型特异性的转录调控，如EGR1靶基因在女性神经元中的异常，展示了其在疾病基因调控研究中的应用价值。
source: biorxiv
selection_source: fresh_fetch
motivation: 现有单细胞多组学整合方法受限于特征异构和配对数据稀缺，难以准确对齐未配对跨模态数据。
method: 提出ECLARE框架，结合多教师集成知识蒸馏与对比学习，利用最优传输损失实现未配对数据的跨模态对齐。
result: 在基准测试中细胞配对准确率领先，并在MDD数据中识别出EGR1、SOX2等因子性别和细胞类型特异性的调控变化。
conclusion: ECLARE为未配对多模态单细胞数据整合提供了稳健方案，可有效揭示疾病相关的基因调控异常。
---

## 摘要
整合多模态单细胞数据（如scRNA-seq和scATAC-seq）是解码基因调控网络的关键。然而，由于特征协调和配对数据数量有限等问题，整合仍然具有挑战性。为了解决这些挑战，我们引入了ECLARE，这是一种新颖的框架，结合了多教师集成知识蒸馏与对比学习，用于整合非配对的单细胞多组学数据。简言之，ECLARE在配对数据集上训练教师模型，以指导学生模型对齐非配对数据，利用精细化的对比目标和基于最优传输的损失实现精确的跨模态对齐。在计算基准测试中，实验表明ECLARE在细胞配对准确性、多模态整合和生物结构保持方面具有竞争性表现，表明多教师知识蒸馏为提升对角整合模型超越其零样本能力提供了有效手段。在生物学案例研究中，我们利用重度抑郁症（MDD）的非配对snRNA-seq和snATAC-seq数据集展示了ECLARE的适用性。首先，我们的结果揭示了在抑郁症中差异调控的转录因子和靶基因组合，具有性别和细胞类型特异性。这些发现进一步揭示了兴奋性神经元中与MDD神经病理学高度相关的基因调控相互作用，例如涉及EGR1、SOX2和NR3C1的相互作用。其次，我们展示了ECLARE能够学习连续数据流形，有助于解读神经发育和疾病中的纵向生物学过程，揭示了作为女性抑郁症潜在调节因子的改变了的神经发育程序，与EGR1靶基因密切相关。总之，我们提出ECLARE作为非配对多模态单细胞数据对角整合的稳健解决方案，能够研究疾病中基因调控的改变。

## Abstract
Integrating multimodal single-cell data such as scRNA-seq and scATAC-seq is key for decoding gene regulatory networks. Still, integration remains challenging due to issues related to feature harmonization and limited quantity of paired data. To address these challenges, we introduce ECLARE, a novel framework combining multi-teacher ensemble knowledge distillation with contrastive learning for integrating unpaired single-cell multi-omic data. Briefly, ECLARE trains teacher models on paired datasets to guide a student model for aligning unpaired data, leveraging a refined contrastive objective and optimal-transport-based loss for precise cross-modality alignment. In computational benchmarking, experiments demonstrate ECLAREs competitive performance in cell pairing accuracy, multimodal integration and biological structure preservation, indicating that multi-teacher knowledge distillation provides an effective means to improve a diagonal integration model beyond its zero-shot capabilities. In biological case studies, we demonstrate ECLAREs applicability using unpaired snRNA-seq and snATAC-seq datasets in major depressive disorder (MDD). Firstly, our results revealed transcription factors and target gene combinations differentially regulated in depression with sex- and cell-type specificity. These findings further reveal gene regulatory interactions in excitatory neurons that are highly relevant to MDD neuropathology, such as those involving EGR1, SOX2, and NR3C1. Secondly, we show that ECLARE can learn continuous data manifolds useful for deciphering longitudinal biological processes in neurodevelopment and disease, revealing altered neurodevelopmental programs as potential regulators of depression in females, strongly associated with EGR1 target genes. Altogether, we propose ECLARE as a robust solution for diagonal integration of unpaired multimodal single-cell data that enables the study of altered gene regulation in disease.