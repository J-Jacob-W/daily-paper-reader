---
title: Virtual phenotypic screening discovers novel scaffolds inhibiting the PI3K/mTOR pathway
title_zh: 虚拟表型筛选发现抑制PI3K/mTOR通路的新型骨架
authors: "Wu, A. P., Yao, H., Hoeckendorf, B., Gaskins, G., Kosaisawe, N., Lu, Z., Hanslovsky, P., Mayba, O., Skelton, N., Scalia, G., Moffat, J. G., Biancalani, T., Hütter, J.-C., Richmond, D."
date: 2026-06-14
pdf: "https://www.biorxiv.org/content/10.64898/2026.06.10.731476v1.full.pdf"
tags: ["query:multi-modal"]
score: 8.0
evidence: 化合物结构与表型成像的多模态共嵌入
tldr: 表型药物发现受限于高通量筛选能力，而现有虚拟筛选多局限于简单表型或小文库。本文提出PhenoCompass多模态共嵌入模型，联合化合物结构与Cell Painting表型成像，实现十亿级虚拟表型筛选。在3.8亿化合物中针对PI3K/mTOR通路进行前瞻性筛选，发现11个新型抑制剂，其中7个经正交验证为结构新颖、机制各异的化合物。该方法展示了不同分子靶点汇聚于共享形态通路信号，建立了高内涵虚拟表型筛选的稳健框架。
source: biorxiv
selection_source: carryover_cache
motivation: 高内涵表型筛选缺乏超高通量可扩展性，虚拟筛选局限于简单表型或小文库，亟需新方法实现大规模虚拟表型筛选。
method: 提出PhenoCompass，多模态共嵌入模型，联合化合物结构和Cell Painting图像，在JUMP数据集训练后，可对十亿级化合物库进行虚拟筛选。
result: 前瞻性筛选3.8亿Enamine REAL化合物，发现11个PI3K/mTOR通路抑制剂，7个经FOXO3A报告实验和激酶抑制实验验证为结构新颖、机制多样的抑制剂。
conclusion: 验证不同分子靶点可共享形态通路特征，PhenoCompass为高内涵虚拟表型筛选提供有效框架，加速先导化合物发现。
---

## 摘要
表型药物发现通过在生理相关细胞系统中发现疾病表型的调节剂，已产生许多首创新药小分子。然而，高内涵表型测定缺乏基于靶点筛选的超高通量可扩展性。虚拟筛选的最新进展为解决这一瓶颈提供了机会，但仅限于简单的表型（如活力）、局限于小型重定位库，或缺乏深入的生物学验证。在此，我们提出PhenoCompass，一种多模态共嵌入模型，对齐化合物结构与高内涵表型成像，从而实现对数十亿化合物库的虚拟表型筛选。在利用包含超过10万份Cell Painting化合物图谱的Morphology联合研究数据集进行训练后，使用历史生物化学高通量筛选数据进行回顾性验证表明，PhenoCompass能够根据化合物的生化靶点结合能力对其进行排序。利用PhenoCompass，我们对38亿个Enamine REAL化合物进行了前瞻性筛选，寻找PI3K/mTOR通路的抑制剂，该通路是一个关键的信号级联，其异常激活是常见的肿瘤驱动因素。此次搜索识别出11种新型化合物，具有通路一致的Cell Painting读数及多样化的骨架，富集度是训练集的54倍。使用FOXO3A报告基因测定和直接激酶抑制的交叉验证实验证实了七种结构新颖的抑制剂，具有不同的作用机制。这些结果突出了不同分子靶点图谱在共享的形态学通路特征上的收敛，并确立了PhenoCompass作为高内涵表型虚拟筛选的稳健框架。

## Abstract
Phenotypic drug discovery has yielded many first-in-class small-molecule drugs by discovering modulators of disease phenotypes in physiologically relevant cellular systems. However, high-content phenotypic assays lack the ultra-high-throughput scalability of target-based screens. Recent advances in virtual screening present an opportunity to address this bottleneck, but have been limited to simple phenotypes like viability, restricted to small repurposing libraries, or lack in-depth biological validation. Here, we present PhenoCompass, a multimodal co-embedding model that aligns compound structures and high-content phenotypic imaging to enable virtual phenotypic screening over billion-compound libraries. Following training on the Joint Undertaking in Morphology dataset with more than 100,000 Cell Painting compound profiles, retrospective validation with historical biochemical high-throughput screening data demonstrates that PhenoCompass ranks compounds according to their biochemical target engagement. Leveraging PhenoCompass, we performed a prospective screen of 3.8 billion Enamine REAL compounds for inhibitors of PI3K/mTOR pathway, a critical signaling cascade whose aberrant activation is a common tumor driver. This search identified 11 novel compounds with pathway-consistent Cell Painting readout and diverse scaffolds, a 54-fold enrichment over the training set. Orthogonal validation experiments using a FOXO3A reporter assay and direct kinase inhibition confirmed seven structurally novel inhibitors with distinct mechanisms of action. These results highlight the convergence of diverse molecular target profiles onto a shared morphological pathway signature and establish PhenoCompass as a robust framework for high-content phenotypic virtual screening.