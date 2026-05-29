---
title: Estimating mutual information and Pearson correlation on neural evoked responses
title_zh: 估计神经诱发反应的互信息和皮尔逊相关性
authors: "Hukari, A., Cotroneo, S. F., Salmelin, R."
date: 2026-05-26
pdf: "https://www.biorxiv.org/content/10.64898/2026.05.21.727057v1.full.pdf"
tags: ["query:eeg-ode-ln"]
score: 6.0
evidence: 神经诱发响应相似性估计方法，适用于EEG
tldr: 神经诱发响应中的时序变异限制了皮尔逊相关对信号相似性的检测。本研究系统比较皮尔逊相关与三种互信息估计器在模拟和真实脑磁图数据上的表现，发现两者对不同信号特性存在灵敏度权衡。互信息在恰当参数设置下能捕获复杂依赖，而皮尔逊相关在低噪声时更可靠。我们提出自适应下界和阈值策略，为选择相似性度量提供实用指导。
source: biorxiv
selection_source: fresh_fetch
motivation: 时序变异削弱皮尔逊相关对信号相似性的检测，互信息可捕获非线性依赖但估计器缺乏共识。
method: 系统比较样本皮尔逊相关与三种常用互信息估计器，在模拟和真实脑磁图数据上测试。
result: 揭示不同度量对信号特性的灵敏度权衡；低噪声时皮尔逊相关可靠，互信息需特定参数稳定。
conclusion: 提出互信息参数选择与阈值策略，指导神经诱发时间序列相似性度量的选择与解读。
---

## 摘要
在神经诱发反应中，当相同的功能反应在不同的试验、不同的实验条件或由不同的传感器记录时，可以观察到反应时间或持续时间的微小变化。这些变化限制了基于相关性的方法检测信号之间相似性的能力。互信息（MI）提供了一种替代的相似性度量，能够捕捉线性和非线性依赖关系，但由于连续数据的估计器缺乏共识，且对估计器在真实信号上行为的理解有限，其实用性受到阻碍。

在这项工作中，我们通过系统比较样本皮尔逊相关性与三种最常见的MI估计器，研究了如何估计神经诱发反应的相似性。我们使用模拟信号和真实的脑磁图数据描述了它们的行为。在模拟中，估计器针对一系列反映神经诱发反应真实变化的变换进行了测试。随后，我们提出了定义相似性估计的自适应下界以及分析不同估计器产生的相似性排序的指南。

我们的发现揭示了度量敏感性与不同信号特性之间的权衡。我们确认皮尔逊相关性在描述低噪声信号的线性关系方面是可靠的，并确定了稳定MI估计器的参数设置，使其能够捕捉复杂的信号依赖关系。这些结果共同为互信息引入了实用的参数选择和阈值策略，并为在神经诱发时间序列分析中选择和解释相似性度量提供了指导。

## Abstract
In neural evoked responses, small variations in the timing or duration of responses can be observed when the same functional response is recorded in different trials, different experimental conditions or by different sensors. These variations limit the ability of correlation-based methods to detect similarities between signals. Mutual information (MI) provides an alternative similarity measure, capable of capturing both linear and non-linear dependencies, yet its practical use is hindered by lack of consensus on estimators for continuous data and the limited understanding of the behavior of the estimators on realistic signals.

In this work, we investigate how to estimate the similarity of neural evoked responses by systematically comparing sample Pearson correlation with three of the most common MI estimators. We describe their behavior using both simulated signals and real magnetoencephalographic data. In the simulations, the estimators are tested against a set of transformations that depict realistic changes in neural evoked responses. Subsequently, we propose guidelines for defining adaptive lower bounds on the similarity estimates and analyzing the similarity rankings induced by the different estimators.

Our findings reveal trade-offs between measures sensitivity and different signal properties. We confirm that Pearson correlation is reliable in describing linear relationships for low-noise signals, and we identify parameter settings that stabilize MI estimators, enabling them to capture complex signal dependencies. Together, these results introduce practical parameter choices and thresholding strategies for mutual information and provide guidance for selecting and interpreting similarity measures in the analysis of neural evoked time series.