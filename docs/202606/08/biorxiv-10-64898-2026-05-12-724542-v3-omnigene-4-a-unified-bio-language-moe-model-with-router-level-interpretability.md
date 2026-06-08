---
title: "OmniGene-4: A Unified Bio-Language MoE Model with Router-Level Interpretability"
title_zh: "OmniGene-4: 具有路由器级别可解释性的统一生物语言MoE模型"
authors: "Wang, L."
date: 2026-06-04
pdf: "https://www.biorxiv.org/content/10.64898/2026.05.12.724542v3.full.pdf"
tags: ["query:multi-modal"]
score: 7.0
evidence: 统一生物语言MoE模型，多模态处理语言与生物序列
tldr: "多模态生物大语言模型常黑箱运作，难以理解其如何回答基于序列的问题。OmniGene-4基于Gemma-4-26B-A4B的MoE架构，通过路由器状态分析揭示：继续预训练贡献96%的专家分化，门控选择模态而专家计算答案。模型在远程同源性任务达82.60%，超越ESM-2等基线，并扩展至视觉模态仍保持性能。该工作为生物基础模型提供了机械透明性与经济高效的实现路径。"
source: biorxiv
selection_source: fresh_fetch
motivation: 现有生物多模态大模型缺乏内部机制的可解释性，可能导致误导性实验决策，需要一种能揭示模型如何路由和计算生物知识的方法。
method: 在Gemma-4-26B-A4B（128专家/层，top-8路由）上构建OmniGene-4，通过继续预训练和监督微调得到统一生物语言MoE，并记录每层路由器状态进行分解分析，进一步扩展视觉模态形成OmniGene-4-MM。
result: "远程同源性82.60%（比ESM-2 3B高28个百分点），标准同源性99.40%，BixBench 93.66%；3Di/DSSP预测达78.6%/100%；多模态扩展以1.5 GPU天完成，保留同源性能力并获得化学结构理解和视觉问答能力。"
conclusion: OmniGene-4揭示了MoE模型中路由器选择模态、专家计算答案的机制，且该机制在模态扩展下稳健重现，以极少计算量实现强基准，推动了可解释、经济高效的生物基础模型发展。
---

## 摘要
共同处理自然语言和生物序列（DNA、蛋白质、结构字母）的多模态大语言模型实际上如何回答生物学问题，特别是那些依赖残基层次模式而非文献回忆的序列基础问题？我们引入了 OmniGene-4，这是一个基于 Gemma-4-26B-A4B（每层128个专家，前8路由）的统一生物语言混合专家基础模型，并利用其离散路由器状态来剖析这一问题。通过挂接八个任务家族中的每个路由器，我们提供了生物MoE的首次路由器层面分解：继续预训练（CPT）占跨任务专家差异化的96%，监督微调（SFT）占4%，分别重塑中间层和输出层。在蛋白质同源任务家族内，每对路由分歧低于0.04（跨任务为0.23），表明序列基础决策发生在专家计算内部而非门控处——门控选择模态，专家计算答案。该管道产生了强劲的基准：远程同源性82.60%（相比ESM-2 3B、MMseqs2、DIAMOND高出28-31个百分点）；标准同源性99.40%；BixBench（一般生物学知识）93.66%。双头架构添加了每个残基的3Di/DSSP分类器（78.6%/100%）。为了探究所发现的迁移机制在模态扩展下是否稳健，我们进一步将模型扩展到 OmniGene-4-MM，通过视觉塔和三阶段LoRA管道（总共1.5 GPU天）添加四种视觉模态（化学结构图像、医学/病理图像、图表）。该多模态模型保留了同源性能力（标准85%，远程69.5%），并获得了化学家可理解的结构理解（Vis-CheBI20功能组标题描述96%），同时消耗的计算量比近期专门的MoE生物模型少约四个数量级。这项工作描述了多模态生物基础模型如何获取、路由和保留序列感知能力——这对下一代科学大语言模型至关重要。

更大的图景。

同时阅读人类语言和生物序列（DNA、蛋白质）的现代AI模型通常像黑箱：我们看到它们的答案，但看不到产生答案的内部机制。这对生物学至关重要，因为一个错误但措辞自信的答案可能误导一个耗时数月、花费数万美元的实验。我们使用混合专家架构——一个变压器，其中每个令牌在每一层被路由到128个专门子网络的一小部分——使这种内部机制变得清晰。通过记录每个输入激活了哪些专家，我们表明将生物学特定的预训练添加到通用语言模型中会导致路由自发地将网络划分为特定模态的子网络，并且当我们进一步扩展模型以处理分子图像、医学图像和图表图像时，同样的划分重新出现。同一模型实现了蛋白质同源性准确性，超过了经典的序列比对工具（MMseqs2、DIAMOND）和最近的蛋白质语言模型（ESM-2 3B），同时消耗的计算量比近期专门的MoE生物模型少约四个数量级。这项工作朝着生物学基础模型迈出了一步，这些模型在模态覆盖范围、机制透明度和经济可复现性方面同时具有广度，可由最大工业实验室以外的团队实现。

## Abstract
How do multi-modal large language models that jointly process natural language and biological sequences (DNA, protein, structural alphabets) actually answer biological questions, especially sequence-grounded questions whose answer depends on residue-level patterns rather than literature recall? We introduce OmniGene-4, a unified bio-language Mixture-of-Experts foundation model on Gemma-4-26B-A4B (128 experts/layer, top-8 routing), and use its discrete router state to dissect this question. By hooking every router across eight task families, we provide the first router-level decomposition for a biological MoE: continued pretraining (CPT) accounts for 96% of cross-task expert differentiation and supervised fine-tuning (SFT) for 4%, reshaping middle and output layers respectively. Within the protein-homology task family, per-pair routing divergence stays below 0.04 (vs 0.23 cross-task), implying that sequence-grounded decisions occur inside expert computation rather than at the gate -- the gate selects the modality, the experts compute the answer. The pipeline yields strong benchmarks: remote-homology 82.60% (vs ESM-2 3B, MMseqs2, DIAMOND by 28-31 pp); standard homology 99.40%; BixBench (general biological-knowledge) 93.66%. A dual-head architecture adds per-residue 3Di/DSSP classifiers (78.6%/100%). To probe whether the discovered transfer mechanism is robust under modality scaling, we further extend the model to OmniGene-4-MM, adding four vision modalities (chemical-structure images, medical/pathology imagery, charts) via a vision tower and a three-stage LoRA pipeline at 1.5 GPU-days total. The multi-modal model preserves the homology capability (85% standard, 69.5% remote) and acquires chemist-readable structure understanding (96% on Vis-CheBI20 functional-group captioning) while consuming roughly four orders of magnitude less compute than recent specialized MoE bio-models. The work characterizes how multi-modal bio-foundation models acquire, route, and preserve sequence-aware capability -- central to the next generation of scientific large language models.

O_TEXTBOXThe bigger picture.

Modern AI models that read both human language and biological sequences (DNA, proteins) often behave like black boxes: we see their answers but not the inner mechanism that produced them. This matters for biology, where a wrong but confidently worded answer can mislead an experiment that costs months and tens of thousands of dollars. We use Mixture-of-Experts architecture -- a transformer where each token is routed to a small subset of 128 specialized sub-networks at every layer -- to make this internal mechanism legible. By logging which experts are activated for each input, we show that adding biology-specific pre-training to a general-purpose language model causes the routing to spontaneously partition the network into modality-specific sub-networks, and that the same partitioning re-emerges when we further extend the model to also process molecular images, medical images, and chart images. The same model achieves protein-homology accuracy that surpasses classical sequence-alignment tools (MMseqs2, DIAMOND) and recent protein language models (ESM-2 3B), at roughly four orders of magnitude less compute than recent specialized MoE bio-models. The work is a step toward foundation models for biology that are simultaneously broad in modality coverage, mechanistically transparent, and economically reproducible by groups outside the largest industrial labs.

C_TEXTBOX