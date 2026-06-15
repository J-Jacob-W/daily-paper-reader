---
title: A multi-agent system for spine MRI report generation from multi-sequence imaging
title_zh: 基于多序列成像的脊柱MRI报告生成的多智能体系统
authors: "Xiao, Z., Yang, J., Sun, G., Zhang, H., Xu, H., Yao, Y., Miller, Z. D., King, W. E., Kanani, M. M., Andre, J. B., Chu, S., Zhang, M., Kinahan, P. E., Cross, N. M., Wang, S."
date: 2026-06-11
pdf: "https://www.biorxiv.org/content/10.64898/2026.06.07.730703v1.full.pdf"
tags: ["query:multi-modal"]
score: 7.0
evidence: 基于多序列影像的脊柱MRI报告生成多智能体系统，利用多模态数据融合
tldr: "脊柱MRI报告生成需整合多序列影像，现有方法难以兼顾序列特异性。本文提出SpineAgent多智能体框架，基于DINOv3编码器和持续训练策略，利用32047名患者数据预训练，在17个脊柱病变预测任务上AUROC平均提升10.8%。框架集成37个专业智能体实现诊断、定位和检索，并通过报告智能体生成可解释报告，经放射科医生评估达到领先性能。"
source: biorxiv
selection_source: fresh_fetch
motivation: 脊柱MRI多序列解读耗时且复杂，现有方法无法有效融合多序列信息并保留序列特异性诊断特征。
method: 预训练两种DINOv3编码器处理T1/T2序列，通过持续训练学习合成器嵌入其他序列，形成患者级多序列表征；进一步构建37个专业智能体负责不同子任务，最终由报告智能体整合生成完整报告。
result: "在17个脊柱病变预测任务上AUROC平均比最优基线高10.8%，跨制造商和跨队列泛化性优秀，且支持病理定位和多模态检索。"
conclusion: SpineAgent通过分解报告生成子任务并利用多序列表征，实现了准确、可解释且泛化性强的脊柱MRI报告生成。
---

## 摘要
脊柱疾病是全球疼痛和残疾的主要原因之一。脊柱磁共振成像（MRI）是临床评估的核心，但其解读仍然复杂且耗时，需要整合多个成像序列和解剖区域的信息。尽管近期在自动化MRI分析方面取得了进展，但有效结合多序列数据同时保留序列特异性诊断信息仍然是一个未解决的挑战。

在此，我们提出SpineAgent，一个基于多序列基础模型的脊柱MRI报告生成的多智能体框架，该模型在32,047名患者和453,683个MRI序列的常规临床数据上训练，总共包含13,441,191张MRI切片。为适应不同模式的序列，我们首先分别在T1和T2加权序列上预训练两个基于DINOv3的编码器。然后，我们引入一种持续训练策略，学习一个合成器，利用T1和T2编码器嵌入其他序列的图像，生成整合跨MRI序列各种信号的患者级嵌入。利用这些嵌入，SpineAgent实现了最先进的性能，在17个脊柱状况预测任务中，平均AUROC比最佳竞争方法提高10.8%，并在跨厂商和跨队列评估中展现出强大的泛化能力。除了分类，SpineAgent通过识别与发现相关的切片和分割病理区域来实现病理定位。它还支持多模态图像-报告检索，为可扩展和可解释的MRI报告生成提供了坚实基础。

我们进一步将这些经过验证的SpineAgent能力集成到37个专门智能体中，用于状况诊断、病理区域定位和临床相似病例检索。最后，我们将它们的输出作为结构化标记纳入一个端到端训练用于报告生成的医学报告智能体中。通过自动评估指标和五位放射科医生的专家评估，SpineAgent在脊柱MRI报告生成中取得了领先性能。

总之，SpineAgent引入了一种用于多序列脊柱MRI理解的持续训练方法。通过将报告生成分解为由专门智能体处理的临床基础子任务，SpineAgent框架能够在不同的成像序列和解剖区域中实现准确、可解释且可泛化的脊柱MRI报告。

## Abstract
Spinal pathology is a leading cause of pain and disability worldwide. Spine magnetic resonance imaging (MRI) is central to clinical evaluation, yet its interpretation remains complex and time-consuming, requiring integration of information across multiple imaging sequences and anatomical regions. Despite recent advances in automated MRI analysis, effectively combining multi-sequence data while preserving sequence-specific diagnostic information remains an open challenge.

Here we present SpineAgent, a multi-agent framework for spine MRI report generation built upon a multi-sequence foundation model trained on routine clinical data from 32,047 patients and 453,683 MRI series, comprising a total of 13,441,191 MRI slices. To accommodate diverse modalities of sequences, we first pre-train two DINOv3-based encoders separately on T1- and T2-weighted sequences. We then introduce a continual training strategy that learns a synthesizer to embed images of other sequences using the T1 and T2 encoders, producing patient-level embedding that integrates various signals across MRI sequences. Using these embeddings, SpineAgent achieves state-of-the-art performance, with mean 10.8% AUROC improvement across 17 spinal condition-prediction tasks compared to the best competing method, and demonstrates strong generalizability under cross-manufacturer and cross-cohort evaluation. Beyond classification, SpineAgent enables pathology localization by identifying findings-relevant slices and segmenting pathological regions. It also supports multimodal image-report retrieval, providing a solid foundation for scalable and explainable MRI report generation.

We further integrate these validated capabilities of SpineAgent into 37 specialized agents for condition diagnosis, pathological-region localization, and clinically-similar-cases retrieval. Finally, we incorporate their outputs as structured tokens within a Medical Report Agent trained end-to-end for report generation. Through both automated metrics and expert evaluation by five radiologists, SpineAgent achieves leading performance in spine MRI report generation.

Together, SpineAgent introduces a continual training approach for multi-sequence spine MRI understanding. By decomposing report generation into clinically grounded subtasks addressed by specialized agents, the SpineAgent framework enables accurate, interpretable and generalizable spine MRI reporting across diverse imaging sequences and anatomical regions.