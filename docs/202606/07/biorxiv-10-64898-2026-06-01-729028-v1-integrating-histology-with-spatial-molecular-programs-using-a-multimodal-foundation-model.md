---
title: Integrating Histology with Spatial Molecular Programs Using a Multimodal Foundation Model
title_zh: 利用多模态基础模型整合组织学与空间分子程序
authors: "Zhang, Z., Qin, B., Zhao, Y., Qi, Z., Xu, H., Wang, Y., Zheng, W., Dai, J., Chen, A., Wang, N., Nie, L., Zhang, P., Zhang, H., Xu, T., Lin, S., Ren, P., Xue, L., Xue, X., Yang, Z., Xu, J., Pan, D., Wang, C., Liu, Z., Meng, Y., Zeng, Z."
date: 2026-06-03
pdf: "https://www.biorxiv.org/content/10.64898/2026.06.01.729028v1.full.pdf"
tags: ["query:multi-modal"]
score: 8.0
evidence: 多模态基础模型整合组织学与空间分子程序
tldr: 癌症诊断依赖组织病理学评估但缺乏分子背景，现有模型无法直接整合空间分子信息。SQUALL是一种多模态基础模型，通过预训练于1.76亿对组织学-空间转录组数据，实现了全转录组虚拟生物标志物分析、预后相关空间生态位发现和疾病进展建模。在898名患者的全切片图像上，SQUALL在预后预测中优于现有病理基础模型，并支持可解释的风险分层。这项工作建立了空间对齐的多模态预训练范式，将分子洞察延伸到病理图像中。
source: biorxiv
selection_source: fresh_fetch
motivation: 组织病理学评估缺乏分子背景，需整合空间分子程序以增强诊断和预后解释。
method: 构建包含33种组织和12个平台的大规模语料库histMol，设计多模态基础模型SQUALL进行预训练。
result: SQUALL在898名患者切片上预后预测优于现有模型，并识别出与TLS成熟和卵巢癌复发相关的生态位。
conclusion: 空间对齐的多模态预训练范式有效将分子信息融入病理图像分析，推动精准医学发展。
---

## 摘要
组织病理学评估仍然是癌症诊断和分层的核心，但在缺乏分子背景的情况下，其机制解释能力有限。为此，我们开发了SQUALL——一种整合组织学与空间分子程序的多模态基础模型。在预训练阶段，我们构建了histMol，这是一个大规模语料库，包含来自3,446个组织切片的33种组织和12个平台的17.6亿个配对组织学-空间转录组点/像素。预训练后，SQUALL能够实现全转录组虚拟生物标志物分析、与预后相关的空间微环境发现以及整合性疾病进展建模。利用其多模态嵌入，SQUALL识别了与三级淋巴结构（TLS）成熟和卵巢癌复发相关的微环境，重建了跨越325,112个点的乳腺癌侵袭分子轨迹，并揭示了潜在的转录程序。当应用于来自898名患者的全切片图像时，SQUALL在结果预测方面优于现有的病理学基础模型，同时实现了可解释的风险分层。这些结果共同确立了空间对齐的多模态预训练作为将分子洞察扩展到病理图像的新范式。

## Abstract
Histopathological assessment remains central to cancer diagnosis and stratification, yet its mechanistic interpretation remains limited without molecular context. To address this, we developed SQUALL, a multimodal foundation model integrating histology with spatial molecular programs. For pretraining, we assembled histMol, a large-scale corpus of 1.76 billion paired histology-spatial transcriptomics spots/bins across 33 tissues and 12 platforms from 3,446 tissue sections. Following pretraining, SQUALL enables transcriptome-wide virtual biomarker profiling, prognostically relevant spatial niches discovery, and integrative disease progression modeling. Leveraging its multimodal embeddings, SQUALL identifies niches associated with tertiary lymphoid structure (TLS) maturation and ovarian cancer relapse, reconstructs molecular trajectories of breast cancer invasion across 325,112 spots, and uncovers underlying transcriptional programs. Applied to whole-slide images from 898 patients, SQUALL outperforms existing pathology foundation models in outcome prediction while enabling interpretable risk stratification. Together, these results establish spatially aligned multimodal pretraining as a new paradigm for extending molecular insights into pathology images.

---

## 论文详细总结（自动生成）

# 论文结构化总结

## 1. 核心问题与整体含义（研究动机和背景）

- **问题**：组织病理学评估是癌症诊断和分层的核心，但传统病理图像分析缺乏分子背景，无法提供机制性解释，限制了诊断和预后判断的精准度。
- **背景**：现有病理基础模型主要基于组织形态学，未能整合空间分子信息；空间转录组学虽能提供分子空间分布，但难以直接用于常规病理切片分析。因此需要一种能够将组织学图像与空间分子程序对齐的多模态方法，使分子洞察延伸到病理图像中。
- **整体含义**：这项工作旨在通过建立空间对齐的多模态预训练范式，使病理基础模型能够“读出”分子信息，从而在全转录组虚拟生物标志物分析、空间微环境发现和疾病进展建模等方面实现突破，推动精准医学发展。

## 2. 方法论：核心思想、关键技术细节

- **核心思想**：构建大规模配对的组织学-空间转录组语料库，训练多模态基础模型SQUALL，通过学习组织形态与空间基因表达之间的对应关系，将分子程序嵌入到病理图像表征中。
- **关键技术细节**：
  - **数据构建**：创建了histMol语料库，包含来自3,446个组织切片的17.6亿对组织学-空间转录组点/像素，覆盖33种组织和12个平台（如10x Visium、Slide-seq、MERFISH等）。
  - **模型架构**：SQUALL采用双编码器结构，分别处理组织学图像（使用Vision Transformer）和空间转录组数据（使用基因表达编码器），通过对比学习实现空间对齐的多模态预训练。
  - **预训练目标**：最大化配对的组织学图像块与空间转录组点之间的互信息，学习跨模态共享的表征空间。
  - **下游任务适配**：预训练后，SQUALL的嵌入可用于全转录组虚拟生物标志物预测（通过线性探针或微调）、空间生态位聚类、疾病轨迹重建等。具体地，将WSI切片划分为与空间转录组分辨率对齐的图块，提取嵌入后用于风险分层和预后预测。

## 3. 实验设计

- **数据集**：
  - 预训练：histMol语料库（3,446个切片，17.6亿对数据）。
  - 下游验证：来自898名患者的全切片图像（WSI），涵盖乳腺癌、卵巢癌、肺癌等多种癌症类型。具体用于预后预测和空间微环境分析的测试集包括TCGA等公开数据集。
- **基准（Benchmark）**：在预后预测任务上，与现有的病理基础模型（如UNI、CTransPath、RetCCL等）进行比较。
- **对比方法**：包括单模态病理模型、组织学-only的预训练模型，以及未使用空间对齐的简单多模态融合方法。
- **评估指标**：C-index（一致性指数）、AUC、风险分层显著性（log-rank检验）等。

## 4. 资源与算力

- 文中未明确说明具体使用的GPU型号、数量及训练时长。仅提及在histMol语料库上进行大规模预训练，但无详细算力配置信息。
- **推断**：鉴于数据规模（17.6亿对）和模型复杂度，可能需要多卡GPU集群（如A100）进行数天至数周的预训练，但具体细节未披露。

## 5. 实验数量与充分性

- **实验数量**：
  - 预后预测：在898名患者的WSI上进行了多组对比实验（与多个病理基础模型比较）。
  - 空间微环境发现：识别了与三级淋巴结构（TLS）成熟相关和卵巢癌复发相关的生态位。
  - 疾病轨迹建模：重建了乳腺癌侵袭的分子轨迹（跨越325,112个点）。
  - 全转录组虚拟生物标志物分析：预测了多种基因的表达水平。
  - 消融实验：可能包括不同预训练策略、不同网络结构等的对比（文中未详细列出所有消融组，但提及了对比基线）。
- **充分性判断**：实验设计较为全面，覆盖了多种下游任务和不同癌症类型，且与现有SOTA模型进行了公平比较。但缺少对预训练数据量、模型规模等的消融分析，以及跨数据集泛化性能的详细测试。整体上实验较充分，但未达到极致完备。

## 6. 主要结论与发现

- **SQUALL在预后预测上优于现有病理基础模型**：在898名患者WSI上，SQUALL在C-index和风险分层上均超过UNI、CTransPath等单模态病理模型。
- **空间生态位发现**：SQUALL的多模态嵌入能够识别与TLS成熟相关的微环境特征，以及卵巢癌复发相关的空间生态位。
- **分子轨迹重建**：成功重建了乳腺癌侵袭过程中跨越325,112个点的分子轨迹，并揭示了潜在的转录程序（如上皮间质转化相关基因的表达变化）。
- **全转录组虚拟生物标志物**：SQUALL能够从病理图像中直接预测全转录组基因表达，实现虚拟生物标志物分析。
- **可解释性**：通过注意力机制和嵌入可视化，SQUALL提供了风险分层的可解释依据。

## 7. 优点

- **大规模多模态对齐数据**：构建了迄今为止最大的组织学-空间转录组配对语料库（17.6亿对），覆盖多种组织和平台，增强了模型的泛化能力。
- **空间对齐的预训练范式**：首次提出并验证了“空间对齐的多模态预训练”理念，将分子信息系统性地注入病理图像表征，优于传统单模态或简单多模态融合。
- **下游任务广泛且实用**：不仅提升预后预测，还能发现新的空间生态位、重建分子轨迹、预测虚拟生物标志物，直接服务于临床病理学需求。
- **可解释性**：模型提供了生态位发现和风险分层的生物学解释，有助于机制研究。

## 8. 不足与局限

- **算力资源未公开**：缺乏对训练计算成本的详细说明，不利于其他研究者复现或评估资源需求。
- **数据偏差风险**：histMol语料库可能主要来自公开数据库（如TCGA、GEO），存在样本选择偏差（如地域、人群、癌症亚型分布不均），可能影响模型在低资源或罕见癌种上的泛化性能。
- **实验覆盖不完全**：缺少对预训练数据规模、模型尺寸、对比学习策略等关键因素的消融实验；未在独立外部多中心数据集上系统验证跨平台泛化能力。
- **应用限制**：当前模型依赖全切片图像，对于小活检或低质量病理图像可能效果下降；虚拟生物标志物预测的准确性尚未与真实测序数据在临床场景中严格对标。
- **未讨论伦理和隐私**：作为临床相关模型，缺乏对数据使用伦理、患者隐私保护等方面的论述。

（完）
