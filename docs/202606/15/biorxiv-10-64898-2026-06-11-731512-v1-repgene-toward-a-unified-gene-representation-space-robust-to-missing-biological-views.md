---
title: "RepGene: Toward a Unified Gene Representation Space Robust to Missing Biological Views"
title_zh: RepGene：迈向对缺失生物学视图鲁棒的统一基因表示空间
authors: "Hou, H., Xia, T., Hu, L., Qin, H., Zhang, Y., Li, Y., Fang, S., Cao, L."
date: 2026-06-15
pdf: "https://www.biorxiv.org/content/10.64898/2026.06.11.731512v1.full.pdf"
tags: ["query:multi-modal"]
score: 6.0
evidence: 多模态融合以应对缺失生物视图
tldr: 现有基因嵌入多为模态特异，难以在缺失视图下比较或重用。RepGene提出轻量级单分支框架，通过适配器、共享编码器、存在感知融合和自监督跨视图目标，将基因组、转录、蛋白质、文本和单细胞五种视图映射到统一表示空间。在固定特征设置下训练与评估，发现该表示在完整模态时表现良好，且在缺失任一视图时性能下降有限，甚至单视图推理仍具信息。本研究作为可行性验证，为统一基因表示学习提供了鲁棒性基线。
source: biorxiv
selection_source: fresh_fetch
motivation: 解决多视图基因嵌入在模态缺失时难以比较和重用的问题，探索构建统一共享的基因表示空间的可行性。
method: 采用轻量级单分支框架，由模态适配器、共享编码器、存在感知融合和自监督跨视图目标组成，映射五种生物视图。
result: 在完整模态下性能有竞争力，缺失任一视图时性能变化有限，单视图推理仍非平凡。
conclusion: 作为可行性研究，表明统一基因表示空间在缺失视图下具有鲁棒性，为后续研究提供基线。
---

## 摘要
基因可以通过多种异质的生物学视图来描述，包括基因组序列、转录本序列、蛋白质序列、文本知识和单细胞表达背景，然而现有的基因嵌入在很大程度上仍然是模态特定的，当许多视图不可用时难以比较或重用。我们研究了一个更窄但实际重要的问题：来自这些不同源的预训练嵌入是否能被组织成一个共享的基因表示接口，该接口在严重的模态缺失条件下仍然可用。为了研究这个问题，我们提出了RepGene，一个轻量级的单分支框架，它结合了模态适配器、共享编码器、存在感知融合和自监督跨视图目标，将五种生物学视图映射到一个潜在空间中。我们的目标不是声称一种新的多模态学习原理或证明其优于所有更简单的融合策略，而是提供一个初步的技术实例，用于测试在固定特征设置下这种共享接口是否可行。在一个两阶段协议下，RepGene在冻结的上游嵌入上进行自监督训练，并通过下游线性探测进行评估，我们发现初步证据表明，学习到的表示在全模态设置中具有广泛的竞争力，并且在推理时仅观察到部分模态子集时仍能提供信息。我们研究中最强的信号是缺失视图下的鲁棒性：当移除一种模态时，平均性能变化通常有限，甚至在评估的基准体系中，单视图推理仍然具有非平凡的意义。这些结果并没有解决统一的生物学表示学习问题，并且应结合不完整的简单融合基线、有限的架构消融、基准依赖性和可能的上游特征暴露来解读。因此，我们将RepGene定位为一项可行性研究，并为更强比较、更广泛基准和泄露感知验证提供了一个起点。

## Abstract
Genes can be described through multiple heterogeneous biological views, including genomic sequence, transcript sequence, protein sequence, textual knowledge, and single-cell expression context, yet existing gene embeddings remain largely modality-specific and difficult to compare or reuse when many views are unavailable. We study a narrower but practically important question: whether pretrained embeddings from these distinct sources can be organized into a shared gene representation interface that remains usable under severe missing-modality conditions. To investigate this question, we introduce RepGene, a lightweight single-branch framework that combines modality adapters, a shared encoder, presence-aware fusion, and self-supervised cross-view objectives to map five biological views into one latent space. Our goal is not to claim a new multimodal learning principle or to establish superiority over all simpler fusion strategies, but to provide an initial technical instantiation for testing whether such a shared interface is feasible in a fixed-feature setting. Under a two-stage protocol in which RepGene is trained self-supervised on frozen upstream embeddings and evaluated by downstream linear probing, we find preliminary evidence that the learned representation is broadly competitive in the full-modality setting and remains informative when only partial modality subsets are observed at inference time. The strongest signal in our study is robustness under missing views: average performance changes are often limited when one modality is removed, and even single-view inference remains non-trivial in the evaluated benchmark regime.These results do not resolve unified biological representation learning, and they should be interpreted in light of incomplete simple-fusion baselines, limited architectural ablation, benchmark dependence, and possible upstream feature exposure. We therefore position RepGene as a feasibility study and a starting point for stronger comparisons, broader benchmarks, and leakage-aware validation.