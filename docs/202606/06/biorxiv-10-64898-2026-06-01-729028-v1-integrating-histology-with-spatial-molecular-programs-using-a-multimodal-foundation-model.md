---
title: Integrating Histology with Spatial Molecular Programs Using a Multimodal Foundation Model
title_zh: 利用多模态基础模型整合组织学与空间分子程序
authors: "Zhang, Z., Qin, B., Zhao, Y., Qi, Z., Xu, H., Wang, Y., Zheng, W., Dai, J., Chen, A., Wang, N., Nie, L., Zhang, P., Zhang, H., Xu, T., Lin, S., Ren, P., Xue, L., Xue, X., Yang, Z., Xu, J., Pan, D., Wang, C., Liu, Z., Meng, Y., Zeng, Z."
date: 2026-06-03
pdf: "https://www.biorxiv.org/content/10.64898/2026.06.01.729028v1.full.pdf"
tags: ["query:multi-modal"]
score: 7.0
evidence: 多模态基础模型整合组织学与空间转录组学，是多模态学习和融合的强方法
tldr: 组织病理评估缺乏分子上下文，难以揭示机制。为此，提出多模态基础模型SQUALL，在17.6亿对组织学-空间转录组数据上预训练。它可进行全转录组虚拟生物标志物分析、发现预后相关的空间微环境，并重建乳腺癌侵袭分子轨迹。在898例患者全切片图像上，SQUALL优于现有病理基础模型，实现了可解释的风险分层。该工作建立了空间对齐多模态预训练新范式，将分子洞察扩展到病理图像。
source: biorxiv
selection_source: fresh_fetch
motivation: 组织病理评估缺乏分子机制解释，需整合空间分子信息以提升诊断和分层。
method: 构建大规模配对数据集histMol（17.6亿对），预训练多模态模型SQUALL对齐组织学与空间转录组。
result: "SQUALL预测转录组、发现TLS成熟及卵巢癌复发相关微环境，重建325,112个点上的乳腺癌侵袭轨迹，预后优于现有模型。"
conclusion: 空间对齐多模态预训练为病理图像提供分子洞察，开启可解释风险分层新范式。
---

## 摘要
组织病理学评估仍是癌症诊断和分层的关键，但缺乏分子背景限制了其机制性解读。为此，我们开发了 SQUALL，一种整合组织学与空间分子程序的多模态基础模型。在预训练阶段，我们构建了 histMol，一个包含来自 3,446 个组织切片的 33 种组织和 12 个平台的 17.6 亿对组织学-空间转录组学斑块/区域的大规模语料库。预训练后，SQUALL 能够实现全转录组虚拟生物标志物分析、预后相关的空间生态位发现以及整合性疾病进展建模。利用其多模态嵌入，SQUALL 识别出与三级淋巴结构 (TLS) 成熟和卵巢癌复发相关的生态位，重建了跨越 325,112 个斑块的乳腺癌侵袭分子轨迹，并揭示了潜在的转录程序。应用于来自 898 名患者的全切片图像时，SQUALL 在结果预测上优于现有病理基础模型，同时实现了可解释的风险分层。总之，这些结果确立了空间对齐的多模态预训练作为将分子见解扩展到病理图像的新范式。

## Abstract
Histopathological assessment remains central to cancer diagnosis and stratification, yet its mechanistic interpretation remains limited without molecular context. To address this, we developed SQUALL, a multimodal foundation model integrating histology with spatial molecular programs. For pretraining, we assembled histMol, a large-scale corpus of 1.76 billion paired histology-spatial transcriptomics spots/bins across 33 tissues and 12 platforms from 3,446 tissue sections. Following pretraining, SQUALL enables transcriptome-wide virtual biomarker profiling, prognostically relevant spatial niches discovery, and integrative disease progression modeling. Leveraging its multimodal embeddings, SQUALL identifies niches associated with tertiary lymphoid structure (TLS) maturation and ovarian cancer relapse, reconstructs molecular trajectories of breast cancer invasion across 325,112 spots, and uncovers underlying transcriptional programs. Applied to whole-slide images from 898 patients, SQUALL outperforms existing pathology foundation models in outcome prediction while enabling interpretable risk stratification. Together, these results establish spatially aligned multimodal pretraining as a new paradigm for extending molecular insights into pathology images.