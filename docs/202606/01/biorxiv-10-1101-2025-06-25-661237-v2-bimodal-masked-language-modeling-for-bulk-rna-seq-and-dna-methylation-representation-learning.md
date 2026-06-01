---
title: Bimodal masked language modeling for bulk RNA-seq and DNA methylation representation learning
title_zh: 面向批量RNA测序与DNA甲基化表示学习的双模态掩码语言建模
authors: "Gelard, M., Benkirane, H., Pierrot, T., Richard, G., Cournede, P.-H."
date: 2026-05-29
pdf: "https://www.biorxiv.org/content/10.1101/2025.06.25.661237v2.full.pdf"
tags: ["query:multi-modal"]
score: 6.0
evidence: RNA-seq和DNA甲基化的双模态表示学习；通用多模态学习方法
tldr: 肿瘤多模态数据整合面临高维挑战，现有单模态模型难以充分利用转录组和表观遗传互补信息。本文提出双模态掩码语言模型，联合学习RNA-seq和DNA甲基化表示，采用高效架构减少内存占用。双模态嵌入在癌症类型分类和生存预测上达到最优性能，且对模态缺失场景具有鲁棒性。该模型为临床多模态数据整合提供了有效且实用的学习框架。
source: biorxiv
selection_source: fresh_fetch
motivation: 现有单模态模型无法充分利用转录组和表观遗传互补信息，且高维多模态整合面临计算和鲁棒性挑战。
method: 采用掩码语言建模自监督，设计双模态Transformer架构，通过参数共享和序列截断减少内存占用。
result: 双模态嵌入在癌症分类和生存分析上超越单模态基线，且在模态缺失时仍保持高性能。
conclusion: 该模型为临床多模态数据整合提供鲁棒且高效的解决方案，提升了实际应用适应性。
---

## 摘要
肿瘤学家越来越依赖多种模态来建模疾病的复杂性。在这一背景下，转录组和表观遗传数据已被证明特别有用，并在临床应用中发挥着日益重要的作用。然而，将它们整合到多模态模型中仍然是一个挑战，特别是考虑到它们的高维度。在这项工作中，我们提出了一种新颖的双模态模型，该模型利用掩码语言建模的自监督方式，联合学习批量RNA测序和DNA甲基化的表示。我们实现了一种架构，减少了通常由纯Transformer模型在处理长序列时的内存占用。我们证明了所获得的双模态嵌入可用于微调癌症类型分类和生存模型，相比单模态模型达到了最先进的性能。此外，我们引入了一个鲁棒的学习框架，即使在模态缺失的情况下也能保持下游任务性能，增强了模型在真实临床环境中的适用性。

## Abstract
Oncologists are increasingly relying on multiple modalities to model the complexity of diseases. Within this landscape, transcriptomic and epigenetic data have proven to be particularly instrumental and play an increasingly vital role in clinical applications. However, their integration into multimodal models remains a challenge, especially considering their high dimensionality. In this work, we present a novel bimodal model that jointly learns representations of bulk RNA-seq and DNA methylation leveraging self-supervision from masked language modeling. We implement an architecture that reduces the memory footprint usually attributed to purely transformer-based models when dealing with long sequences. We demonstrate that the obtained bimodal embeddings can be used to fine-tune cancer-type classification and survival models that achieve state-of-the-art performance compared to unimodal models. Furthermore, we introduce a robust learning framework that maintains downstream task performance despite missing modalities, enhancing the models applicability in real-world clinical settings.