---
title: BAYESIAN STATE-SPACE MODEL FOR JOINT INFERENCE OF OSCILLATORY DYNAMICS AND POINT-PROCESS COUPLING
title_zh: 用于振荡动力学和点过程耦合联合推断的贝叶斯状态空间模型
authors: "Zheng, B., Brincat, S., Donoghue, J., Miller, E., Brown, E."
date: 2026-06-19
pdf: "https://www.biorxiv.org/content/10.64898/2026.06.15.732402v1.full.pdf"
tags: ["query:eeg-ode-ln"]
score: 6.0
evidence: 神经信号振荡与点过程耦合的联合推断
tldr: 经典尖峰-场耦合度量（SFC、PLV）独立估计LFP频谱与耦合，无法利用尖峰时序提升频谱分辨率。本文提出Joint SSMT，一个贝叶斯状态空间框架，将窄带LFP建模为潜在连续时间过程，尖峰通过伯努利-逻辑模型关联复数谱状态，从而联合推断LFP谱图和耦合强度。模拟显示其能准确恢复耦合强度、去噪谱图并解析精细结构；在丙泊酚麻醉数据中识别出SFC/PLV无法分辨的特定慢振荡耦合；扩展至试验结构数据后，在联想学习任务中揭示了海马和前额叶皮层的频率特异性耦合。该方法提供了比经典度量更频率特异性的耦合估计，并内置不确定性量化，为神经振荡耦合分析提供了新工具。
source: biorxiv
selection_source: fresh_fetch
motivation: 经典方法分离估计频谱与耦合，无法利用尖峰时序改善LFP谱估计，且耦合频率分辨率低，需要联合推断框架。
method: 构建贝叶斯状态空间模型，将窄带LFP视为潜在连续时间复数过程，尖峰通过伯努利-逻辑函数与其相位和幅值耦合，实现谱图和耦合强度的联合推断。
result: 在模拟和两个灵长类数据集上，Joint SSMT比PLV和SFC提供更频率特异性的耦合估计，并给出原理性不确定性区间。
conclusion: Joint SSMT实现了更精确的尖峰-场耦合推断，适用于多种实验设计，有助于理解神经振荡在认知和麻醉状态下的耦合机制。
---

## 摘要
在多种行为与生理条件下，尖峰时间和局部场电位（LFP）振荡在特定频带内表现出相位耦合。经典度量如尖峰-场相干性（SFC）和相位锁定值（PLV）量化了这种耦合，但LFP谱的估计独立于尖峰时序。我们提出了Joint SSMT，一种贝叶斯状态空间框架，可联合推断LFP谱图和尖峰-场耦合强度。该模型将窄带LFP活动视为随时间连续演化的潜在过程，尖峰序列通过伯努利-逻辑斯蒂模型与复值谱状态相关联。在模拟中，Joint SSMT准确恢复耦合强度，去噪谱图，并利用尖峰时序解析LFP中的精细时间结构。应用于丙泊酚麻醉数据时，该模型在特定的慢振荡频率处识别出耦合，而SFC和PLV仅报告宽低频耦合。我们将Joint SSMT扩展到试次结构实验，并应用于联想学习任务中的灵长类记录，揭示了海马体和前额叶皮层中频率特异性耦合。我们还推导了SFC和PLV作为生成模型参数的闭式表达式。在模拟和两个灵长类数据集的测试中，Joint SSMT相比经典PLV和SFC提供了更具频率特异性的耦合估计，并具有合理的的不确定性量化。

## Abstract
Under a range of behavioral and physiological conditions, spike times and local field potential (LFP) oscillations exhibit phase coupling within specific frequency bands. Classical measures such as spike--field coherence (SFC) and the phase-locking value (PLV) quantify this coupling but estimate the LFP spectrum independently of spike timing. We introduce Joint SSMT, a Bayesian state-space framework that jointly infers LFP spectrograms and spike--field coupling strength. The model treats narrowband LFP activity as a latent process evolving in continuous time, with spike trains linked to the complex spectral state through a Bernoulli--logistic model. In simulations, Joint SSMT accurately recovers coupling strength, denoises the spectrogram, and uses spike timing to resolve fine temporal structure in the LFP. Applied to propofol anesthesia data, the model identifies coupling at a specific slow-oscillation frequency where SFC and PLV report only broad low-frequency coupling. We extend Joint SSMT to trial-structured experiments and apply it to primate recordings during an associative learning task, revealing frequency-specific coupling in hippocampus and prefrontal cortex. We also derive closed-form expressions for SFC and PLV as functions of the generative model parameters. Across simulations and two primate datasets, Joint SSMT provides more frequency-specific coupling estimates with principled uncertainty quantification than classical PLV and SFC.