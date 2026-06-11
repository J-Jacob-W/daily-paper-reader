---
title: Cross-modal applications of a neuromorphic olfactory learning algorithm
title_zh: 跨模态的神经形态嗅觉学习算法应用
authors: "Helde, M., Dimitrov, A."
date: 2026-06-11
pdf: "https://www.biorxiv.org/content/10.64898/2026.06.02.727939v2.full.pdf"
tags: ["query:multi-modal"]
score: 6.0
evidence: 神经形态学习算法跨模态应用于图像和声音
tldr: "神经形态嗅觉算法被跨模态应用于图像和声音识别。对图像直接使用NIST数字数据集，对声音经gammatone滤波转换为频谱图并修改算法处理。对所有模态实施PCA降维保留约90%方差。算法在顺序伽马周期中成功实现一次性在线学习，但PCA表示与模板相似度不高。结果表明该算法具备跨模态泛化能力，但PCA降维可能削弱嗅觉模拟的准确性。"
source: biorxiv
selection_source: fresh_fetch
motivation: 探索嗅觉神经算法在图像和声音识别中的跨模态应用潜力，验证其通用性。
method: 针对图像和声音分别预处理：图像直接使用，声音经gammatone滤波和PCA降维，修改算法处理频谱图列。
result: 算法在图像和声音模态实现一次性在线学习，但PCA表示与模板相似度低。
conclusion: 跨模态嗅觉算法有效，但PCA表征能力有限，需改进降维方法以提升相似度。
---

## 摘要
我们将一种嗅觉神经形态算法改编用于图像和声音识别。为此，我们针对每种模态定制了特定的预处理流程。对于图像，我们直接使用NIST数字数据集。对于声音，我们使用来自Google Speech Command数据集的样本。对每个声音样本应用伽马通滤波器以降低短音频样本的噪声，并将时间声音信号转换为位置频率信号。随后修改单刺激测试算法，以处理从声音文件获得的伽马通滤波器频谱图中提取的列上的音频处理。我们还对所有模态实施了PCA，保留了约90%的方差。结果表明，在连续的“嗅觉”伽马周期中，该算法也成功地在图像和声音模态上实现了单次在线学习。然而，对于所有三种模态，PCA表示并未达到与其对应模板的高度相似性。

## Abstract
We adapted an olfactory neuromorphic algorithm to image and sound recognition. To achieve this, we carried out specific preprocessing procedures that were tailored to each modality. For images, we used the NIST digits dataset directly. For sound, we used samples from the Google Speech Command dataset. A gammatone filter was applied to each to reduce the noise of the short audio sample and convert the temporal sound signal to a positional frequency signal. The single stimulus test algorithm was then modified to handle audio processing on extracted columns from a gammatone filter spectrogram obtained from the sound file. We also implemented PCA for all modalities, retaining around 90% of the variance. The results showed that over sequential 'olfactory' gamma cycles, the algorithm successfully achieved one-shot online learning over the image and sound modalities as well. However, PCA representations did not attain high similarities to their corresponding templates for all three modalities.