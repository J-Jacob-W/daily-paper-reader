---
title: Parameter scaling of multivariate Granger causality
title_zh: 多元格兰杰因果关系的参数缩放
authors: "Pirenne, T., Florin, E."
date: 2026-06-02
pdf: "https://www.biorxiv.org/content/10.1101/2025.10.01.679714v2.full.pdf"
tags: ["query:eeg-ode-ln"]
score: 7.0
evidence: 稀疏多元格兰杰因果方法用于EEG信号分析
tldr: 高维神经数据导致多变量自回归模型因果估计不可靠。为解决可扩展性问题，提出稀疏多变量Granger因果方法，利用因果连接的稀疏性约束候选空间。模拟实验表明，sMVGC在保持估计精度的同时显著改善参数可扩展性，样本需求随信号数增加而增长。工作提供了实际参数范围和模型选择指导，有助于推进全脑因果分析应用。
source: biorxiv
selection_source: fresh_fetch
motivation: 高维全脑数据使MVAR模型估计困难，需可扩展的因果推断方法。
method: 基于因果稀疏假设，限制候选连接空间，提出稀疏MVAR Granger因果方法。
result: sMVGC在模拟中提高了参数可扩展性，保持了估计精度，样本需求随信号数增长。
conclusion: 提供了实际参数范围和模型选择指导，促进高维神经数据因果分析。
---

## 摘要
估计信号之间的因果相互作用可以深入理解其动力学，因果推断已广泛应用于电生理数据以阐明大脑通信。多变量自回归模型（MVAR）构成了大多数因果估计方法的基础。然而，全脑数据的高维性使得MVAR难以可靠估计，将维度降低到合理范围会影响因果推断。为了解决这些可扩展性限制，我们开发了稀疏多元格兰杰因果关系（sMVGC），这是一种基于真实信号间因果连接是稀疏的假设的新方法，从而限制了候选搜索空间并提高了可扩展性。为了从经验上推动sMVGC，我们模拟了具有已知因果关系的电生理数据，并建模了样本数、信号数和MVAR阶数如何影响当前算法的性能和计算时间。所有算法至少随这些参数二次缩放，但在对信号与样本数量的敏感性上有所不同，而准确推断所需的样本数量随信号数量缩放。在这些发现的指导下，sMVGC在保持估计精度的同时提高了参数可扩展性，我们为实际分析提供了实用的参数范围和模型选择指导。

## Abstract
Estimating causal interactions between signals provides unique insights into their dynamics, and causal inference has been widely applied to electrophysiological data to elucidate brain communication. Multivariate autoregressive models (MVAR) form the basis of most causal estimation methods. However, the high dimensionality of whole-brain data renders MVARs difficult to estimate reliably, and reducing the dimensions to a reasonable range affects causal inference. To address these scalability limitations, we develop sparse Multivariate Granger Causality (sMVGC), a novel method premised on the assumption that true causal connections between signals are sparse, thereby constraining the candidate search space and improving scalability. To motivate sMVGC empirically, we simulate electrophysiological data with known causalities and model how the number of samples, signals, and MVAR order affect the performance and computation time of current algorithms. All algorithms scale at least quadratically with these parameters, yet differ in their sensitivity to signal versus sample count, and the sample requirements for accurate inference scale with the number of signals. Guided by these findings, sMVGC improves parameter scalability while preserving estimation accuracy, and we provide practical parameter ranges and model selection guidance for real-world analyses.