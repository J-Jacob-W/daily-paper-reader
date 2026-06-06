---
title: Cross-modal applications of a neuromorphic olfactory learning algorithm
title_zh: 一种神经形态嗅觉学习算法的跨模态应用
authors: "Dimitrov, A., Helde, M. L."
date: 2026-06-05
pdf: "https://www.biorxiv.org/content/10.64898/2026.06.02.727939v1.full.pdf"
tags: ["query:multi-modal"]
score: 6.0
evidence: 跨模态学习算法
tldr: "本研究将神经形态嗅觉学习算法跨模态应用于图像和声音识别。对图像直接使用NIST数字数据集，对声音采用Google语音命令数据集，通过gammatone滤波将时域信号转换为频域信号，并进行PCA降维保留约90%方差。实验表明，该算法在三个模态上均实现一次性在线学习，但PCA特征与模板的相似度较低。研究证明嗅觉算法可迁移至其他模态，为神经形态计算提供新方向。"
source: biorxiv
selection_source: fresh_fetch
motivation: 探索神经形态嗅觉学习算法在图像和声音识别任务中的跨模态适用性。
method: "针对图像和声音分别进行gammatone滤波等预处理，修改算法处理频谱图，并采用PCA降维至保留约90%方差。"
result: 算法在三个模态均实现一次性在线学习，但PCA表示与对应模板的相似度较低。
conclusion: 神经形态嗅觉算法具备跨模态学习能力，但PCA特征表示需进一步改进以提升相似度。
---

## 摘要
我们将一种嗅觉神经形态算法改编用于图像和声音识别。为此，我们针对每种模态进行了特定的预处理流程。对于图像，我们直接使用了NIST手写数字数据集。对于声音，我们使用了谷歌语音指令数据集中的样本。对每个声音样本应用了伽马通滤波器，以减少短音频样本的噪声，并将时间声音信号转换为位置频率信号。随后，我们对单刺激测试算法进行了修改，以处理从声音文件获得的伽马通滤波器语谱图中提取的列上的音频处理。我们还对所有模态实施了主成分分析，保留了大约90%的方差。结果表明，在连续的“嗅觉”伽马周期中，该算法也成功地在图像和声音模态上实现了一次性在线学习。然而，对于所有三种模态，主成分分析表示与其对应模板的相似度并不高。

## Abstract
We adapted an olfactory neuromorphic algorithm to image and sound recognition. To achieve this, we carried out specific preprocessing procedures that were tailored to each modality. For images, we used the NIST digits dataset directly. For sound, we used samples from the Google Speech Command dataset. A gammatone filter was applied to each to reduce the noise of the short audio sample and convert the temporal sound signal to a positional frequency signal. The single stimulus test algorithm was then modified to handle audio processing on extracted columns from a gammatone filter spectrogram obtained from the sound file. We also implemented PCA for all modalities, retaining around 90% of the variance. The results showed that over sequential 'olfactory' gamma cycles, the algorithm successfully achieved one-shot online learning over the image and sound modalities as well. However, PCA representations did not attain high similarities to their corresponding templates for all three modalities.