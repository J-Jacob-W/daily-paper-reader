---
title: "Single-trial Endpoint-summary Measures do not Capture P300 Coupling in the Visual Oddball Paradigm: a Pseudotrial-controlled, Cross-validated Study"
title_zh: 单次试验终点总结测量无法捕捉视觉奇异球范式中的P300耦合：一项伪试验控制、交叉验证研究
authors: "Biber, E."
date: 2026-06-11
pdf: "https://www.biorxiv.org/content/10.64898/2025.12.17.694588v4.full.pdf"
tags: ["query:eeg-ode-ln"]
score: 8.0
evidence: 单试次EEG解码P300方法
tldr: 单试次ERP分析中，早期窗口汇总度量与P300振幅的耦合可能源于EEG时间自相关而非刺激锁定过程。本研究通过伪试次控制，在视觉oddball范式下检验端点汇总度量（均值、均方根、复杂度等）与P300的真实耦合。结果发现通道间耦合增强由背景噪声驱动，同通道耦合在所有电极（含眼电）下伪试次不变，表明是通用试次内连续性而非P300特异；复杂度度量群体水平耦合近零但个体方向分裂。结论：端点汇总度量无法捕获群体一致的P300耦合，复杂度度量需个体差异分析方法。
source: biorxiv
selection_source: fresh_fetch
motivation: 检验单试次端点汇总度量在控制EEG自相关后能否捕获真实的P300刺激锁定耦合。
method: 使用ERP CORE视觉P3数据集（N=27），将早期窗口（0-150ms）度量与Pz处P300振幅关联，并用随机延迟的伪试次重估模型，以诊断耦合来源。
result: 同通道耦合（R²≈0.31）在伪试次下不变且存在所有电极，为通用时间连续性；复杂度度量群体耦合近零但个体方向分裂。
conclusion: 端点汇总度量不能捕获群体P300耦合，复杂度度量反映个体差异，需设计对个体差异敏感的分析。
---

## 摘要
单次试验分析事件相关电位有望获取平均处理所丢弃的试次间变异性，许多研究报告早期窗口总结测量与后期成分幅度存在协变关系。然而，这种耦合可能源于连续EEG的时间自相关，而非刺激锁定加工。我们探究了传统终点总结测量家族——将时间窗口压缩为单一值的测量，包括平均幅度、均方根、方差、信号复杂度测量（排列熵、样本熵、Lempel-Ziv复杂度）以及Hjorth参数——在控制自相关后，是否能在主动视觉奇异球中捕捉到关于P300幅度的真实刺激锁定信息。通过分析ERP CORE视觉P3数据集（N=27；1084个试次，213个目标试次和871个标准试次，以实验条件为协变量），我们将每个早期窗口（0-150毫秒）测量与Pz处的P300幅度相关联，并在同一记录中随机延迟放置的伪试验上重新估计每个模型；诊断指标是该替换下的变化方向，而非原始效应量。跨通道幅度和能量耦合在伪试验替换下增强，表明依赖于背景结构。大的同通道耦合（R²≈0.31）在替换下不变，且出现在每个电极（包括眼电通道），将其识别为一般性的试次内时间连续性，而非P300特定过程。复杂度测量在群体水平上携带近乎零的耦合，但每个受试者的斜率方向分化显著。独立数据集（不同实验室和硬件；相同范式）再现了同通道连续性结果（N=90名参与者；83名用于伪试验拟合）以及跨复杂度测量的方向分化的个体模式。因此，一旦控制自相关，终点总结测量无法捕捉一致的群体水平P300耦合；复杂度家族携带个体特异性耦合，在群体水平上相互抵消，这激发了对个体差异敏感的分析设计。

## Abstract
Single-trial analysis of event-related potentials promises access to the trial-to-trial variability that averaging discards, and many studies report early-window summary measures that covary with later component amplitudes. Such couplings can, however, arise from the temporal autocorrelation of continuous EEG rather than from stimulus-locked processing. We asked whether the conventional family of endpoint-summary measures those that collapse a time window to a single value, including mean amplitude, root-mean-square, variance, signal-complexity measures (permutation entropy, sample entropy, Lempel-Ziv complexity), and Hjorth parameters, captures genuine stimulus-locked information about P300 amplitude in the active visual oddball once autocorrelation is controlled. Analyzing the ERP CORE visual P3 dataset (N = 27; 1,084 trials, 213 target and 871 standard, with experimental condition as a covariate), we related each early-window (0-150 ms) measure to P300 amplitude at Pz and re-estimated every model on pseudotrials placed at random latencies in the same recording; the direction of change under this substitution, not the raw effect size, is the diagnostic. Cross-channel amplitude and energy couplings strengthened under pseudotrial substitution, indicating dependence on background structure. Large same-channel coupling (R2 {approx} 0.31) was unchanged under substitution and present at every electrode, including the eye channels, identifying it as general within-trial temporal continuity rather than a P300-specific process. Complexity measures carried near-zero population-level coupling but large, directionally split per-subject slopes. An independent dataset (different laboratory and hardware; same paradigm) reproduced the same-channel continuity result (N = 90 participants; 83 for pseudotrial fits) and the directionally split per-subject pattern across complexity measures. Endpoint-summary measures therefore do not capture consistent population-level P300 coupling once autocorrelation is controlled; the complexity family carries person-specific coupling that cancels at the population level, motivating analytic designs sensitive to individual differences.