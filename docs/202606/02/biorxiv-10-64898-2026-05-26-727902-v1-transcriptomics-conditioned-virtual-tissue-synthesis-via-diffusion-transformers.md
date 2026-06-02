---
title: Transcriptomics-Conditioned Virtual Tissue Synthesis via Diffusion Transformers
title_zh: 基于扩散变换器的转录组学条件虚拟组织合成
authors: "Vlachas, P., Nonchev, K., Koelzer, V., Ratsch, G."
date: 2026-05-29
pdf: "https://www.biorxiv.org/content/10.64898/2026.05.26.727902v1.full.pdf"
tags: ["query:multi-modal"]
score: 6.0
evidence: 通过跨注意力利用基因表达和形态条件合成
tldr: "空间转录组学将H&E组织形态与基因表达关联，但现有生成模型未能利用该耦合。本文提出STMDiT扩散Transformer，通过自适应层归一化和交叉注意力融合基因表达，采用双分类器自由引导训练。在黑色素瘤队列上，基因条件使FID从330.7降至252.9，AUC达0.267（超无GE基线）。使用DeepSpots预测伪标签零样本迁移至TCGA SKCM，FID改善57点。该方法首次实现基因表达驱动的虚拟组织合成，为计算病理学假设检验提供新工具。"
source: biorxiv
selection_source: fresh_fetch
motivation: 现有模型未能从转录组剖面合成组织图像，STMDiT旨在利用基因表达与形态耦合实现条件生成。
method: 基于PixCell的扩散Transformer，通过自适应层归一化和逐块交叉注意力嵌入基因表达，训练时使用独立模态丢弃的双分类器自由引导。
result: 在10x TuPro Visium黑色素瘤中，GE条件改善FID（252.9 vs 330.7）和AUC（0.267 vs 0.229）；DeepSpots伪标签零样本迁移至TCGA SKCM，FID从747.1降至690.0。
conclusion: 基因表达条件可生成形态独特的组织图像，支持虚拟组织模拟，为计算病理学提供可迁移的合成能力。
---

## 摘要
空间转录组学将苏木精-伊红（H&E）组织形态与空间分辨基因表达（GE）相结合。然而，利用这种耦合从转录组谱合成组织图像的生成模型仍然很少。我们提出STMDiT（空间转录组学与形态扩散变换器），一种扩散变换器，它以形态嵌入和转录组谱为条件联合合成H&E组织病理学图像块。基于PixCell（Yellapragada等人，2025），我们通过自适应层归一化和逐块交叉注意力，从冻结的CancerFoundation编码器（Theus等人，2024）中整合基因表达，并在独立模态丢弃下采用双无分类器引导进行训练。在10x TuPro Visium黑色素瘤队列上，与无GE的PixCell-B基线相比，GE条件化改善了图像质量（最佳FID = 252.9 vs 330.7）和转录组保真度（最佳AUC = 0.267 vs 0.229，达到真实图像块上限的82%）。使用DeepSpots预测转录组学伪标签（PTPL）进行训练，可零样本迁移到TCGA SKCM，这是一个分布外（OOD）的仅含H&E的黑色素瘤队列：PTPL-XAttn-PMA-B达到FID = 690.0，比无GE基线（747.1）提高了57个点，且模型内GE消融效应为ΔOOD = +309.5，实现了超越原生空间转录组学覆盖范围的虚拟组织合成。我们的结果表明，基因表达条件化能产生形态上独特的组织图像，并支持用于计算病理学假设检验的虚拟组织模拟。

## Abstract
Spatial transcriptomics couples hematoxylin and eosin (H&E) tissue morphology with spatially resolved gene expression (GE). However, generative models that exploit this coupling to synthesize tissue images from transcriptomic profiles remain scarce. We present STMDiT (Spatial Transcriptomics and Morphology Diffusion Transformer), a diffusion transformer that synthesizes H&E histopathology patches conditioned jointly on morphological embeddings and transcriptomic profiles. Building on PixCell (Yellapragada et al., 2025), we integrate gene expression from a frozen CancerFoundation encoder (Theus et al., 2024) through adaptive layer normalization and per-block cross-attention, and we train under dual classifier-free guidance with independent modality dropout. On the 10x TuPro Visium melanoma cohort, GE conditioning improves both image quality over the no-GE PixCell-B baseline (best FID = 252.9 vs 330.7) and transcriptomic fidelity (best AUC = 0.267 vs 0.229, reaching 82% of the real-tile ceiling). Training with DeepSpots predicted-transcriptomics pseudo-labels (PTPL) uniquely transfers zero-shot to TCGA SKCM, an out-of-distribution (OOD) H&E-only melanoma cohort: PTPL-XAttn-PMA-B reaches FID = 690.0, a 57-point improvement over the no-GE baseline (747.1), with a within-model GE-ablation effect of {Delta}OOD = +309.5, enabling virtual tissue synthesis beyond native spatial-transcriptomics coverage. Our results indicate that gene-expression conditioning produces morphologically distinct tissue images and supports virtual tissue simulation for hypothesis testing in computational pathology.