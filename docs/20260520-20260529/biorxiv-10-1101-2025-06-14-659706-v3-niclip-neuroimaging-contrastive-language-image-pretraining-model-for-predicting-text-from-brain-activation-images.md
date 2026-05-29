---
title: "NiCLIP: Neuroimaging contrastive language-image pretraining model for predicting text from brain activation images"
title_zh: "NiCLIP: 神经影像对比语言-图像预训练模型——从脑激活图像预测文本"
authors: "Peraza, J. A., Kent, J. D., Nichols, T. E., Poline, J.-B., de la Vega, A., Laird, A. R."
date: 2026-05-23
pdf: "https://www.biorxiv.org/content/10.1101/2025.06.14.659706v3.full.pdf"
tags: ["query:multi-modal"]
score: 6.0
evidence: 神经影像中的对比语言-图像预训练
tldr: 预测脑激活图对应的认知过程是神经科学长期难题。现有元分析方法依赖有限文本度量，无法捕捉语义。本文提出NiCLIP，基于CLIP框架用23000篇全文文章训练文本与脑图对齐模型。实验表明，全文本比摘要、精炼认知本体比粗粒度映射效果更优，微调LLM略有增益。NiCLIP能准确预测HCP多认知域任务（如情感、语言），并刻画杏仁核等脑区功能，但对个体噪声图局限。该方法为功能解码提供定量工具，促进假设生成。
source: biorxiv
selection_source: fresh_fetch
motivation: 现有神经影像元分析方法难以从文本中捕捉语义，需结合大语言模型与对比学习以对齐文本与脑激活图。
method: 提出NiCLIP，利用23000篇神经科学全文文章训练CLIP模型，并引入精炼认知本体及微调LLM（如BrainGPT）。
result: NiCLIP在群体激活图上准确预测多种认知任务，且优于摘要输入；对个体噪声图表现有限。
conclusion: NiCLIP是定量功能解码的重要进展，为神经科学研究提供强大工具。
---

## 摘要
多年来，从脑激活图中预测认知过程一直是神经科学领域的一个未解问题。元分析功能解码方法旨在通过提供与特定脑区相关的行为特征的定量估计来解决这一问题。现有方法在神经影像元分析中面临固有挑战，尤其是在整合出版物中的文本信息时，因为它们依赖有限的指标，无法捕捉文本的语义上下文。大语言模型（LLMs）与先进深度对比学习模型（如CLIP）的结合，用于对齐文本与图像，彻底革新了神经影像元分析，可能为功能解码挑战提供解决方案。在这项工作中，我们提出了NiCLIP，一个对比语言-图像预训练模型，能够从脑激活模式中预测认知任务、概念和领域。我们利用超过23,000篇神经科学文章训练了一个用于文本-脑关联的CLIP模型。对NiCLIP预测的评估显示，使用全文文章而非摘要，以及使用具有精确任务-概念-领域映射的策展认知本体论时，性能达到最优。此外，微调的大语言模型（如BrainGPT模型）在性能上略优于其基础大语言模型对应版本。我们的结果表明，NiCLIP能够准确预测来自人脑连接组计划提供的群体水平激活图的认知任务（涉及多个领域，如情感、语言、运动），并精确刻画特定脑区（包括杏仁核、海马体和颞顶联合区）的功能角色。然而，NiCLIP在处理噪声较大的个体水平激活图时表现出局限性。NiCLIP代表了神经影像定量功能解码的重要进展，为研究人员提供了假设生成和科学发现的强大工具。

## Abstract
Predicting cognitive processes from brain activation maps has remained an open question within the neuroscience community for many years. Meta-analytic functional decoding methods aim to tackle this issue by providing a quantitative estimation of behavioral profiles associated with specific brain regions. Existing methods face intrinsic challenges in neuroimaging meta-analysis, particularly in consolidating textual information from publications, as they rely on limited metrics that do not capture the semantic context of the text. The combination of large language models (LLMs) with advanced deep contrastive learning models (e.g., CLIP) for aligning text with images has revolutionized neuroimaging meta-analysis, potentially offering solutions to functional decoding challenges. In this work, we present NiCLIP, a contrastive language-image pretrained model that predicts cognitive tasks, concepts, and domains from brain activation patterns. We leveraged over 23,000 neuroscientific articles to train a CLIP model for text-to-brain association. Evaluation of NiCLIP predictions revealed that performance is optimized when using full-text articles instead of abstracts, as well as a curated cognitive ontology with precise task-concept-domain mappings. Furthermore, fine-tuned LLMs (e.g., BrainGPT models) modestly outperform their base LLM counterparts. Our results indicated that NiCLIP accurately predicts cognitive tasks from group-level activation maps provided by the Human Connectome Project across multiple domains (e.g., emotion, language, motor) and precisely characterizes the functional roles of specific brain regions, including the amygdala, hippocampus, and temporoparietal junction. However, NiCLIP showed limitations with noisy subject-level activation maps. NiCLIP represents a significant advancement in quantitative functional decoding for neuroimaging, offering researchers a powerful tool for hypothesis generation and scientific discovery.