---
title: A multi-agent system for spine MRI report generation from multi-sequence imaging
title_zh: 一种用于多序列脊柱MRI报告生成的多智能体系统
authors: "Xiao, Z., Yang, J., Sun, G., Zhang, H., Xu, H., Yao, Y., Miller, Z. D., King, W. E., Kanani, M. M., Andre, J. B., Chu, S., Zhang, M., Kinahan, P. E., Cross, N. M., Wang, S."
date: 2026-06-11
pdf: "https://www.biorxiv.org/content/10.64898/2026.06.07.730703v1.full.pdf"
tags: ["query:multi-modal"]
score: 7.0
evidence: 用于医学报告生成的多模态基础模型
tldr: "脊柱MRI报告生成面临多序列数据整合难题。SpineAgent框架首先预训练DINOv3编码器处理T1和T2序列，再通过持续训练合成器嵌入其他序列，生成患者级嵌入。基于此构建37个专门智能体执行诊断、定位和检索，最终由医学报告智能体端到端生成报告。在17个预测任务上平均AUROC提升10.8%，跨厂商泛化性强，并支持病理定位与多模态检索。该工作通过分解任务实现了准确、可解释且泛化的脊柱MRI报告生成。"
source: biorxiv
selection_source: fresh_fetch
motivation: 现有方法难以有效整合多序列MRI的互补信息用于脊柱报告生成。
method: 预训练T1/T2双DINOv3编码器，通过持续训练学习合成器嵌入其他序列，构建37个专门智能体并端到端训练报告生成。
result: "17个任务平均AUROC提升10.8%，跨厂商和跨队列泛化优于基线，报告质量经五位放射科医生评估领先。"
conclusion: SpineAgent通过分解任务实现多序列MRI报告的准确、可解释、可泛化生成。
---

## 摘要
脊柱病理是全球疼痛和残疾的主要原因。脊柱磁共振成像（MRI）是临床评估的核心，但其判读复杂且耗时，需要整合多个成像序列和解剖区域的信息。尽管近年来自动化MRI分析取得了进展，但在保留序列特异性诊断信息的同时有效结合多序列数据仍然是一个开放的挑战。

本文提出了SpineAgent，一个基于多序列基础模型构建的脊柱MRI报告生成多智能体框架，该模型在来自32,047名患者和453,683个MRI系列（共13,441,191张MRI切片）的常规临床数据上训练。为了适应不同的序列模态，我们首先在T1和T2加权序列上分别预训练两个基于DINOv3的编码器。然后，我们引入一种持续训练策略，学习一个合成器，利用T1和T2编码器嵌入其他序列的图像，生成整合MRI序列间各种信号的患者级嵌入。利用这些嵌入，SpineAgent达到了最先进的性能，在17个脊柱状况预测任务中，与最佳竞争方法相比，平均AUROC提高了10.8%，并在跨厂商和跨队列评估中表现出强大的泛化能力。除了分类，SpineAgent通过识别与发现相关的切片和分割病理区域来实现病理定位。它还支持多模态图像-报告检索，为可扩展和可解释的MRI报告生成提供了坚实基础。

我们进一步将SpineAgent的这些经过验证的能力集成到37个专门智能体中，用于条件诊断、病理区域定位和临床相似病例检索。最后，我们将它们的输出作为结构化标记纳入一个端到端训练的医学报告智能体，用于报告生成。通过自动评估指标和五位放射科专家的评估，SpineAgent在脊柱MRI报告生成中实现了领先性能。

综上所述，SpineAgent为多序列脊柱MRI理解引入了一种持续训练方法。通过将报告生成分解为由专门智能体处理的临床基础子任务，SpineAgent框架能够在不同的成像序列和解剖区域实现准确、可解释且可泛化的脊柱MRI报告。

## Abstract
Spinal pathology is a leading cause of pain and disability worldwide. Spine magnetic resonance imaging (MRI) is central to clinical evaluation, yet its interpretation remains complex and time-consuming, requiring integration of information across multiple imaging sequences and anatomical regions. Despite recent advances in automated MRI analysis, effectively combining multi-sequence data while preserving sequence-specific diagnostic information remains an open challenge.

Here we present SpineAgent, a multi-agent framework for spine MRI report generation built upon a multi-sequence foundation model trained on routine clinical data from 32,047 patients and 453,683 MRI series, comprising a total of 13,441,191 MRI slices. To accommodate diverse modalities of sequences, we first pre-train two DINOv3-based encoders separately on T1- and T2-weighted sequences. We then introduce a continual training strategy that learns a synthesizer to embed images of other sequences using the T1 and T2 encoders, producing patient-level embedding that integrates various signals across MRI sequences. Using these embeddings, SpineAgent achieves state-of-the-art performance, with mean 10.8% AUROC improvement across 17 spinal condition-prediction tasks compared to the best competing method, and demonstrates strong generalizability under cross-manufacturer and cross-cohort evaluation. Beyond classification, SpineAgent enables pathology localization by identifying findings-relevant slices and segmenting pathological regions. It also supports multimodal image-report retrieval, providing a solid foundation for scalable and explainable MRI report generation.

We further integrate these validated capabilities of SpineAgent into 37 specialized agents for condition diagnosis, pathological-region localization, and clinically-similar-cases retrieval. Finally, we incorporate their outputs as structured tokens within a Medical Report Agent trained end-to-end for report generation. Through both automated metrics and expert evaluation by five radiologists, SpineAgent achieves leading performance in spine MRI report generation.

Together, SpineAgent introduces a continual training approach for multi-sequence spine MRI understanding. By decomposing report generation into clinically grounded subtasks addressed by specialized agents, the SpineAgent framework enables accurate, interpretable and generalizable spine MRI reporting across diverse imaging sequences and anatomical regions.