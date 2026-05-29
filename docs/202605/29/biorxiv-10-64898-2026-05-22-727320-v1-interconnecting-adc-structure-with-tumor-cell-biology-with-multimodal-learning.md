---
title: Interconnecting ADC Structure with Tumor Cell Biology with Multimodal Learning
title_zh: 基于多模态学习连接ADC结构与肿瘤细胞生物学
authors: "Mslati, H., Wilson, M., Naeinipour, M., Coulombe, G., Ezzine, M., Yuen, T., Bari, O., Singh, H., Tam, R., Sheff, J., Gentile, F., Leyton, J."
date: 2026-05-27
pdf: "https://www.biorxiv.org/content/10.64898/2026.05.22.727320v1.full.pdf"
tags: ["query:multi-modal"]
score: 6.0
evidence: 用于ADC药物反应预测的多模态学习平台
tldr: ADC开发因结构-肿瘤生物学关联不明而失败率高。现有预测框架多依赖基因组数据，缺乏蛋白质信息。本文提出多模态平台，融合ADC结构参数与肿瘤细胞多组学及蛋白质组特征（GENCEP模型），在159个ADC-细胞系组合前瞻性预测中性能超越小分子基准。结果表明蛋白质信息可有效提升ADC细胞毒性预测能力。
source: biorxiv
selection_source: fresh_fetch
motivation: 现有ADC开发因结构-肿瘤生物学关联不清而失败率高，且预测框架仅依赖基因组数据，缺少蛋白质信息。
method: 构建多模态机器学习平台，融合ADC结构参数与肿瘤细胞多组学及蛋白质组数据（GENCEP模型）。
result: 在159个ADC-细胞系组合前瞻性预测中性能超越小分子药物基准，覆盖多种抗原、连接子载荷系统和肿瘤类型。
conclusion: 蛋白质信息多模态集成框架可有效捕获ADC细胞毒性决定因素，为ADC开发提供新工具。
---

## 摘要
抗体药物偶联物（ADC）代表了癌症治疗的重要进展，但其发展仍受限于高失败率，这源于对ADC化学设计如何与肿瘤生物学相互连接的理解不充分。更复杂的是，该领域已收敛于一组冗余的结构组件，以及当前不共享单一作用机制的连接子-载荷系统。现有的药物反应预测框架无法解决这种多维复杂性，主要依赖于基因组输入，而蛋白质水平的生物学难以整合。为解决这一问题，我们开发了一个多模态机器学习平台，通过数千个精选的结构-活性数据点，包括来自1479个人类肿瘤细胞系的多组学图谱和来自独特模型（GENCEP）的蛋白质水平输入（该模型推导出完整的蛋白质组特征），将ADC结构参数与肿瘤细胞生物学相连接。该模型通过盲法回顾性评估进行了验证，并关键地，通过前瞻性预测了涵盖五种抗原、四种机制不同的连接子-载荷系统和八种肿瘤类型的159个ADC-细胞系组合的细胞毒性（其中大多数无先前公开的关联ADC数据）。其性能超越了为小分子治疗模式建立的行业基准，表明基于蛋白质信息的跨模态集成框架能够有效地大规模捕获细胞毒性决定因素。

## Abstract
Antibody-drug conjugates (ADCs) represent a significant advancement in cancer therapy, yet their development remains constrained by high attrition rates driven by an incomplete understanding of how ADC chemical design interconnects with tumor biology. Compounding this challenge, the field has converged on a narrow set of redundant structural components, and current linker-payload systems that do not share a single mechanism of action. Existing drug response prediction frameworks cannot resolve this multidimensional complexity, relying predominantly on genomic inputs while protein-level biology is challenging to integrate. To address this, we developed a multimodal machine learning platform interconnecting ADC structural parameters with tumor cell biology across thousands of curated structure-activity datapoints, including multi-omics profiles from 1,479 human tumor cell lines and protein-level inputs from a unique model (GENCEP) that derives complete proteomic signatures. The model was validated through blinded retrospective evaluation and, critically, large coverage prospective prediction of cytotoxicity across 159 ADC-cell line combinations spanning five antigens, four mechanistically distinct linker-payload systems, and eight tumor types, most with no prior published associated ADC data. Performance surpassed industry benchmarks established for small molecule therapeutic modalities, demonstrating that protein-informed multimodal integrated framework is effective at capturing cytotoxic determinants at scale.