---
title: "Beyond Phase Estimation: A Multidimensional Gating Framework for Robust Real-Time Closed-Loop Neural Stimulation"
title_zh: 超越相位估计：一种用于鲁棒实时闭环神经刺激的多维门控框架
authors: "Zheng, W., Shen, L., Han, B."
date: 2026-05-28
pdf: "https://www.biorxiv.org/content/10.64898/2026.05.26.727783v1.full.pdf"
tags: ["query:eeg-ode-ln"]
score: 8.0
evidence: 基于EEG的实时相位门控框架
tldr: 神经振荡相位广泛用于实时闭环刺激控制，但噪声和因果约束下其可靠性缺乏验证。本文提出多维门控框架MGF，通过评估瞬时幅度、窄带信噪比和频谱峰值比，在因果窗口内决定相位信息是否进入控制。在静息态EEG因果回放中，MGF显著降低两种相位估计器的离散度并抑制灾难性误差。该框架即插即用且与估计器无关，为闭环神经刺激提供更稳健的相位控制方案。
source: biorxiv
selection_source: fresh_fetch
motivation: 现有相位估计在噪声和因果约束下可靠性差，缺乏系统性检验，需鲁棒的门控机制。
method: 提出MGF，基于瞬时幅度、窄带信噪比和频谱峰值比，在因果窗内决定相位信息准入。
result: 静息态EEG上，MGF使Hilbert和端点校正Hilbert估计的相位离散度显著降低，并消除灾难性误差。
conclusion: MGF即插即用且与估计器无关，能增强闭环神经刺激中相位控制的鲁棒性。
---

## 摘要
神经振荡相位被广泛用作实时闭环刺激的控制变量，然而在严格的因果约束和噪声条件下，其有效性很少被系统地检验。我们引入了一种多维门控框架（MGF），它是一个即插即用、估计器无关的模块，通过在严格因果窗口内评估瞬时振幅、窄带信噪比（SNR）和频谱峰值比（PR），来确定相位信息是否应被允许进入控制。通过在公共静息态EEG数据集上进行因果流式重放，我们对比了基于Hilbert的相位估计和端点校正的Hilbert估计（有和无MGF）。在可行的受试者中，MGF显著降低了两种估计器的相位分散性，同时稳健地抑制了灾难性的相位误差。相比之下，无门控的方法在相同条件下表现出系统性失败。

## Abstract
Neural oscillatory phase is widely used as a control variable in real-time closed-loop stimulation, yet its validity under strict causal constraints and noisy conditions has rarely been systematically examined. We introduce a Multidimensional Gating Framework (MGF), a plug-in and estimator-agnostic module that determines whether phase information should be admitted into control by evaluating instantaneous amplitude, narrowband signal-to-noise ratio (SNR), and spectral peak ratio (PR) within a strictly causal window. Using causal streaming replay on a public resting-state EEG dataset, we benchmarked Hilbert based phase estimation and endpoint-corrected Hilbert estimation with and without MGF. Among feasible subjects, MGF significantly reduced phase dispersion for both estimators, while robustly suppressing catastrophic phase errors. In contrast, ungated approaches exhibited systematic failures under the same conditions.