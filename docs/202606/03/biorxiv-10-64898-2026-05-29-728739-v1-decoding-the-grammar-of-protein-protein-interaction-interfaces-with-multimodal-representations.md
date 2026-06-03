---
title: Decoding the Grammar of Protein-Protein Interaction Interfaces with Multimodal Representations
title_zh: 利用多模态表征解码蛋白质-蛋白质相互作用界面的语法
authors: "Cuturello, F., Senci, S., Di Vora, D., Gardinazzi, Y., Villegas Garcia, E. N., Feltrin, A."
date: 2026-06-02
pdf: "https://www.biorxiv.org/content/10.64898/2026.05.29.728739v1.full.pdf"
tags: ["query:multi-modal"]
score: 6.0
evidence: 多模态表示用于蛋白质相互作用预测
tldr: 蛋白质相互作用界面预测对理解细胞过程至关重要。现有方法要么缺乏结构信息，要么难以整合进化上下文。本文提出ESM3-PPISites，利用ESM3多模态表示进行残基级界面分类，在严格去冗余基准上，通过微调小模型显著缩小了与大型专有模型的性能差距，预测精度远超现有方法。将预测结果作为空间约束集成到HADDOCK3对接平台，在Docking Benchmark v5上显著提升了近天然结合构象的识别能力，同时将计算时间降低一个数量级，为高通量结构相互作用组学提供了可扩展范式。
source: biorxiv
selection_source: fresh_fetch
motivation: 现有PPI界面预测方法难以融合结构和进化信息，亟需高效且仅需序列输入的精准预测工具。
method: 基于ESM3蛋白语言模型的多模态表征，采用严格去冗余过滤的监督学习，对残基进行PPI界面分类。
result: 微调的小模型性能接近大型专有版本，精度远超现有方法；预测约束使HADDOCK3对接成功率提升，计算成本降低10倍。
conclusion: 该框架实现了序列驱动的精准PPI界面预测与对接增强，为高通量蛋白质互作网络解析奠定了技术基础。
---

## 摘要
蛋白质-蛋白质相互作用（PPI）调控着关键的细胞过程，因此对相互作用位点的计算识别成为结构生物学中的核心挑战，对蛋白质工程和靶向治疗药物的开发具有重要意义。现有的预测算法包括基于序列的方法（缺乏结构信息）和基于结构的方法（通常难以有效整合进化背景）。在此，我们提出ESM3-PPISites，一个利用ESM3蛋白质语言模型的多模态表征进行PPI界面残基级别分类的有监督模型。为确保无偏评估，我们采用严格的冗余过滤协议，系统性地消除训练数据与精心设计的基准集之间在序列和结构空间中的潜在同源性。我们的发现表明，尽管ESM3最大的专有版本提供了最高的预测能力，但对其小型开放权重版本进行有针对性的微调可显著缩小性能差距。仅需推理时的初级序列数据，ESM3-PPISites便实现了前所未有的准确性，大幅优于当前方法。关键的是，我们通过将这些预测作为空间约束整合到HADDOCK3对接平台中，证明了其实践影响。在使用来自Docking Benchmark v5的12个复合物独立子集进行评估时，我们的预测引导流程相较于从头盲对接显著增强了对近天然结合构象的识别，同时将计算运行时间降低了一个数量级。这一框架为高通量结构相互作用组学建立了一种可扩展的范式。

## Abstract
Protein-protein interactions (PPI) govern essential cellular processes, making the computational identification of interacting sites a central challenge in structural biology, with important implications for protein engineering and the development of targeted therapeutics. Existing prediction algorithms include sequence-based methods, which lack structural information, or structure-based approaches, which often struggle to effectively integrate evolutionary context. Here, we present ESM3-PPISites, a supervised model for residue-level classification of PPI interfaces, leveraging the multimodal representations of the ESM3 Protein Language Model. To ensure a bias-free evaluation, we adopt a stringent redundancy filtering protocol, systematically eliminating latent homology between the training data and a curated benchmark set in both sequence and structural space. Our findings demonstrate that while ESM3 largest proprietary version yields the highest predictive power, targeted fine-tuning of its small open-weight counterpart significantly narrows the performance gap. Requiring only primary sequence data at inference, ESM3-PPISites achieves unprecedented accuracy, vastly outperforming current approaches. Crucially, we demonstrate the practical impact of these predictions by integrating them as spatial restraints within the HADDOCK3 docking platform. When evaluated on an independent subset of 12 complexes from the Docking Benchmark v5, our prediction-guided pipeline strongly enhances the identification of near-native binding poses over ab initio blind docking, while reducing computational runtime by an order of magnitude. This framework establishes a scalable paradigm for high-throughput structural interactomics.