---
title: "OmniGene-4: A Unified Bio-Language MoE Model with Router-Level Interpretability"
title_zh: OmniGene-4：一个具有路由器级别可解释性的统一生物语言MoE模型
authors: "Wang, L."
date: 2026-06-04
pdf: "https://www.biorxiv.org/content/10.64898/2026.05.12.724542v3.full.pdf"
tags: ["query:multi-modal"]
score: 8.0
evidence: 集成自然语言与生物序列的多模态生物语言MoE模型
tldr: "当前多模态语言模型处理生物序列问题时，答案依赖残基模式而非文献回忆，但内部机制不明。我们提出OmniGene-4，基于Gemma-4的混合专家模型，通过路由器状态分解揭示：继续预训练贡献96%的跨任务专家分化，序列决策发生在专家计算而非门控。模型在远程同源性达82.60%，标准99.40%，并扩展至多模态版本OmniGene-4-MM，以极低计算成本保持性能并理解化学结构。"
source: biorxiv
selection_source: fresh_fetch
motivation: 揭示多模态生物大模型如何基于序列模式回答生物问题，而非依赖记忆。
method: 基于Gemma-4构建MoE模型，通过路由器状态分解分析专家分化；扩展多模态版本，用三阶段LoRA融合视觉。
result: "远程同源性82.60%，标准99.40%，BixBench 93.66%；多模态版保留同源能力，化学理解96%。"
conclusion: 门控选择模态，专家计算答案；多模态扩展以极低代价保持序列感知，指导未来科学大模型设计。
---

## 摘要
多模态大语言模型如何联合处理自然语言和生物序列（DNA、蛋白质、结构字母表）并实际回答生物学问题，特别是那些答案依赖于残基级模式而非文献回忆的序列基础问题？我们提出了OmniGene-4，一个基于Gemma-4-26B-A4B（每层128个专家，top-8路由）的统一生物语言混合专家基础模型，并利用其离散的路由器状态来解析这个问题。通过挂钩八个任务族中的每个路由器，我们首次提供了生物MoE的路由器级分解：持续预训练(CPT)占跨任务专家差异化的96%，监督微调(SFT)占4%，分别重塑了中间层和输出层。在蛋白质同源任务族中，每对路由分歧低于0.04（跨任务为0.23），这意味着基于序列的决策发生在专家计算内部而非门控处——门控选择模态，专家计算答案。该流程产生了强劲的基准测试结果：远程同源性82.60%（比ESM-2 3B、MMseqs2、DIAMOND高出28-31个百分点）；标准同源性99.40%；BixBench（通用生物学知识）93.66%。一个双头架构增加了每个残基的3Di/DSSP分类器（78.6%/100%）。为了探究所发现的迁移机制在模态扩展下是否稳健，我们进一步将模型扩展到OmniGene-4-MM，通过视觉塔和三阶段LoRA流程添加了四种视觉模态（化学结构图像、医学/病理图像、图表），总共耗时1.5 GPU天。多模态模型保持了同源性能力（标准85%，远程69.5%），并获得了化学家可读的结构理解能力（Vis-CheBI20官能团描述准确率96%），同时消耗的计算量比近期专门的MoE生物模型少了大约四个数量级。该工作刻画了多模态生物基础模型如何获取、路由和保持序列感知能力——这对下一代科学大语言模型至关重要。

## Abstract
How do multi-modal large language models that jointly process natural language and biological sequences (DNA, protein, structural alphabets) actually answer biological questions, especially sequence-grounded questions whose answer depends on residue-level patterns rather than literature recall? We introduce OmniGene-4, a unified bio-language Mixture-of-Experts foundation model on Gemma-4-26B-A4B (128 experts/layer, top-8 routing), and use its discrete router state to dissect this question. By hooking every router across eight task families, we provide the first router-level decomposition for a biological MoE: continued pretraining (CPT) accounts for 96% of cross-task expert differentiation and supervised fine-tuning (SFT) for 4%, reshaping middle and output layers respectively. Within the protein-homology task family, per-pair routing divergence stays below 0.04 (vs 0.23 cross-task), implying that sequence-grounded decisions occur inside expert computation rather than at the gate --- the gate selects the modality, the experts compute the answer. The pipeline yields strong benchmarks: remote-homology 82.60% (vs ESM-2 3B, MMseqs2, DIAMOND by 28--31 pp); standard homology 99.40%; BixBench (general biological-knowledge) 93.66%. A dual-head architecture adds per-residue 3Di/DSSP classifiers (78.6%/100%). To probe whether the discovered transfer mechanism is robust under modality scaling, we further extend the model to OmniGene-4-MM, adding four vision modalities (chemical-structure images, medical/pathology imagery, charts) via a vision tower and a three-stage LoRA pipeline at 1.5 GPU-days total. The multi-modal model preserves the homology capability (85% standard, 69.5% remote) and acquires chemist-readable structure understanding (96% on Vis-CheBI20 functional-group captioning) while consuming roughly four orders of magnitude less compute than recent specialized MoE bio-models. The work characterizes how multi-modal bio-foundation models acquire, route, and preserve sequence-aware capability --- central to the next generation of scientific large language models.

---

## 论文详细总结（自动生成）

# 论文详细中文总结

## 1. 论文的核心问题与整体含义（研究动机和背景）

- **核心问题**：多模态大语言模型（MLLM）在联合处理自然语言与生物序列（如DNA、蛋白质、结构字母表）时，如何真正回答基于序列的生物学问题？特别是那些答案依赖残基级模式而非文献记忆的问题。模型内部机制（门控与专家如何分工）尚不明确。
- **研究背景**：现有生物大模型（如ESM-2、ProtGPT2）多为纯序列模型，缺乏自然语言理解；而统一语言-生物模型（如GeneTuring、ProtST）虽能回答问题，但内部决策路径不明。同时，多模态扩展（引入化学结构、病理图像等）对序列感知能力的影响未知。
- **整体含义**：该工作揭示了MoE模型中门控（gate）负责选择模态，专家（expert）负责计算具体答案的“路由-计算”分离机制，并为未来科学多模态大模型的设计提供了可解释性指导。

## 2. 论文提出的方法论：核心思想、关键技术细节

- **核心思想**：基于Gemma-4-26B-A4B（每层128个专家，top-8路由）构建双生物语言MoE基础模型，利用其离散路由器状态（router state）进行可解释性分析；再扩展为多模态版本OmniGene-4-MM，验证迁移机制的稳健性。
- **关键技术细节**：
  - **基础模型（OmniGene-4）**：
    - 在Gemma-4-26B-A4B上进行**继续预训练（CPT）**和**监督微调（SFT）**，覆盖8个任务族（蛋白质同源、DNA、RNA、结构字母表、功能描述等）。
    - 设计**路由器挂钩（router hooking）**：在每个transformer层记录每个token的路由选择（哪个专家被激活），从而量化专家在不同任务间的分化程度（路由分歧度量）。
    - 采用**双头架构**：在模型顶层添加两个线性分类头，分别预测每个残基的3Di结构字母和DSSP二级结构，实现残基级结构预测。
  - **多模态扩展（OmniGene-4-MM）**：
    - 集成视觉塔（vision tower）处理四种视觉模态：化学结构图像、医学/病理图像、图表。
    - **三阶段LoRA**：阶段1冻结语言/视觉塔，仅训练投影层；阶段2用LoRA微调语言模型；阶段3联合LoRA微调所有参数。总训练耗时仅1.5 GPU天。
  - **无需额外预训练数据集**，完全基于现有公共数据，使用混合损失函数（包括同源任务对比损失、结构分类交叉熵等）。

## 3. 实验设计：数据集、基准与对比方法

- **数据集与任务族**：
  - 蛋白质同源：远程同源（remote homology）、标准同源（standard homology）
  - 通用生物学知识：BixBench（包含文献记忆型与序列推理型问题）
  - 残基级结构：3Di结构字母预测、DSSP二级结构预测
  - 多模态：Vis-CheBI20（官能团图像描述）、病理图像分类等
- **基准（Benchmark）**：
  - 远程同源性准确率（82.60%）
  - 标准同源性准确率（99.40%）
  - BixBench准确率（93.66%）
  - 残基3Di预测准确率（78.6%），DSSP（100%）
  - 多模态Vis-CheBI20官能团描述准确率（96%）
- **对比方法**：
  - 同源任务：ESM-2 3B、MMseqs2、DIAMOND（对比高出28-31个百分点）
  - 多模态：仅与自身消融对比（各种LoRA阶段变体），未与专门的生物多模态模型（如BioMedCLIP）直接对比（因计算量差异巨大）。

## 4. 资源与算力

- **基础模型训练**：论文未明确给出具体GPU型号和数量，仅说明总训练耗时**1.5 GPU天**（针对多模态扩展阶段）。继续预训练和微调阶段未单独给出资源，但基于Gemma-4-26B-A4B（每层128专家），推测使用了大规模分布式训练（如A100/H100集群），具体信息缺省。
- **多模态扩展**：1.5 GPU天（假设单GPU），计算量比近期专门的MoE生物模型减少了约四个数量级（4 orders of magnitude）。

## 5. 实验数量与充分性

- **主要实验组**：
  - 基础模型：8个任务族的路由器分解分析（每层挂钩），包括CPT vs SFT贡献量化（96% vs 4%）、任务内/间路由分歧比较。
  - 同源任务：远程+标准双基准测试，消融对比（有无CPT/SFT、不同专家数）。
  - 双头架构：3Di/DSSP预测准确率。
  - 多模态：三阶段LoRA消融（分别测试各阶段性能）、视觉模态迁移（化学、病理、图表）。
  - 可解释性实验：可视化专家激活模式、任务嵌入相似度。
- **充分性评估**：实验设计较为全面，覆盖了核心问题（路由器分解）、下游性能、多模态泛化。但有两处不足：1）多模态未与同类模型（如GeneTuring-MM、BioGPT-V）直接比较；2）消融实验仅在自身架构上进行，未对比训练数据规模的影响。总体而言，实验客观且能支撑主要结论。

## 6. 论文的主要结论与发现

- **路由机制发现**：继续预训练（CPT）贡献96%的跨任务专家分化，监督微调（SFT）仅占4%；CPT主要重塑中间层，SFT主要重塑输出层。
- **门控与专家的分工**：在同源任务族内部，每对任务的路由分歧低于0.04，而跨任务分歧高达0.23。这表明**门控负责选择模态（生物 vs 语言），专家内部计算具体的答案**。即顺序序列决策发生在专家计算内部，而非门控处。
- **高性能验证**：远程同源性82.60%（超对比方法28-31个百分点），标准同源性99.40%，BixBench 93.66%。
- **多模态稳健性**：OmniGene-4-MM在极低计算成本下（1.5 GPU天）仍保留同源能力（标准85%、远程69.5%），并获取化学家可读的结构理解（Vis-CheBI20 96%）。
- **整体结论**：多模态生物基础模型通过门控选择模态、专家计算答案的机制获取序列感知能力；该机制在模态扩展下保持稳健，为下一代科学LLM的设计提供可解释性指导。

## 7. 优点

- **方法创新**：首次对生物MoE模型提供路由器级分解，揭示门控与专家的功能分离，具有高可解释性。
- **高效扩展**：多模态版本仅用1.5 GPU天，计算效率极高，远低于同类模型（四个数量级）。
- **性能突出**：在同源任务上显著超越传统方法（ESM-2、MMseqs2），且双头架构实现残基级结构预测。
- **实验设计严谨**：系统性地量化了CPT和SFT对专家分化的贡献，并通过路由分歧度量验证了任务内/间差异。

## 8. 不足与局限

- **实验覆盖局限**：多模态部分未与现有生物多模态模型（如BioMedCLIP、GeneTuring-MM）进行公平对比，仅与自身消融比较；缺少零样本/少样本迁移实验。
- **偏差风险**：训练数据来源未详细说明（是否包含生物文献语料），可能存在数据泄漏风险（如远程同源任务的基准可能部分见于预训练数据）。
- **应用限制**：模型为26B参数（有效4B/每个token），实际部署门槛高；双头架构的3Di/DSSP分类器仅有两个类头，未与专用结构预测模型（如AlphaFold2）比较。
- **可解释性定量化不足**：路由分歧度量仅基于专家选择频率，未分析专家权重或激活值对决策的具体影响。
- **资源信息不完整**：基础模型训练的具体GPU型号、数量、时间未公开，影响复现性。

（完）
