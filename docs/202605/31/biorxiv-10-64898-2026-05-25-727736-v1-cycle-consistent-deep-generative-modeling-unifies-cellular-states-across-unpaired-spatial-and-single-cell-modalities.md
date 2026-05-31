---
title: Cycle-consistent deep generative modeling unifies cellular states across unpaired spatial and single-cell modalities
title_zh: 基于循环一致深度生成模型的跨非配对空间与单细胞模态的细胞状态统一
authors: "Zhang, H., Quinn, J. F., Data Science TeamLab,, Tansey, W."
date: 2026-05-26
pdf: "https://www.biorxiv.org/content/10.64898/2026.05.25.727736v1.full.pdf"
tags: ["query:multi-modal"]
score: 6.0
evidence: 通过循环一致生成模型实现多模态融合
tldr: 空间转录组和单细胞技术分别捕获细胞状态的不同方面，但测量未配对、特征空间不匹配。MultiTME通过空间正则化的循环一致深度生成模型，学习共享隐空间，实现无需配对数据的跨模态翻译。在多个基准上，它优于现有方法，完成空间转录组面板补全和全转录组空间映射，并校正平台偏差。应用于结直肠癌数据集，揭示了单模态无法直接观察的增殖-侵袭肿瘤轴。
source: biorxiv
selection_source: fresh_fetch
motivation: 现有空间与单细胞数据测量未配对、特征空间不匹配，缺乏统一整合框架。
method: 使用空间正则化的循环一致深度生成模型，学习共享隐空间实现无配对跨模态翻译。
result: 在多种基准上超越现有方法，完成空间转录组面板补全和全转录组空间映射，并校正平台偏差。
conclusion: MultiTME高效整合异构多模态数据，揭示单模态无法观察的空间生物学特征。
---

## 摘要
当前的空间和单细胞技术捕捉了细胞状态的互补但不完整的视图，其中转录组、蛋白组和空间信息分布在不同的平台上。非配对的测量、不匹配的特征空间以及模态特异性偏差给整合带来了挑战。我们提出MultiTME，一个多模态框架，通过使用空间正则化的循环一致深度生成模型来整合异质的空间和单细胞数据。通过强制双向映射的一致性，MultiTME学习了一个共享的潜在表示，能够在不需要配对观测或共享特征的情况下实现模态之间的转换。在多个基准测试中，MultiTME优于现有方法，产生准确的跨模态细胞分型，改进空间转录组面板补全，并转移全转录组信息以生成细胞分辨率的空间解析图谱。应用于一个多模态结直肠癌数据集，我们证明MultiTME的整合揭示了一个在单一模态中无法直接观察到的空间连贯的增殖-侵袭性肿瘤轴。在五个多模态空间数据集中，我们展示了MultiTME能够纠正Xenium和CosMx之间的平台特异性偏差，从而促进跨数据集的协调，并实现泛癌空间研究。MultiTME的代码可在https://github.com/tansey-lab/multitme获取。

## Abstract
Current spatial and single-cell technologies capture complementary but incomplete views of cellular state, with transcriptomic, proteomic, and spatial information distributed across distinct platforms. Integration is challenged by unpaired measurements, mismatched feature spaces, and modality-specific biases. We present MultiTME, a multimodal framework that integrates heterogeneous spatial and single-cell data using a spatially-regularized, cycle-consistent deep generative model. By enforcing consistency of bidirectional mappings, MultiTME learns a shared latent representation that enables translation between modalities without requiring paired observations or shared features. Across benchmarks, MultiTME outperforms existing methods, produces accurate cross-modal cell typing, improves spatial transcriptomic panel completion, and transfers whole-transcriptome information to generate spatially resolved maps at cellular resolution. Applied to a multimodal colorectal cancer dataset, we demonstrate that MultiTME integration reveals a spatially coherent proliferative-invasive tumor axis not directly observable within single modalities. Across five multimodal spatial datasets, we show MultiTME can correct for platform-specific biases between Xenium and CosMx, thereby facilitating cross-dataset harmonization and enabling pan-cancer spatial studies. Code for MultiTME is available at https://github.com/tansey-lab/multitme.