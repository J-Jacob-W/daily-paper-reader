---
title: "Beyond the Forest and the Trees: Overlooking the Overlooked Terrain of Neural State Dynamics"
title_zh: 超越森林与树木：忽视被忽视的神经状态动力学地形
authors: "Asai, T., Kashihara, S., Chiyohara, S."
date: 2026-06-09
pdf: "https://www.biorxiv.org/content/10.64898/2026.06.04.729738v1.full.pdf"
tags: ["query:eeg-ode-ln"]
score: 6.0
evidence: EEG微状态分析方法
tldr: 传统EEG微状态分析基于聚类模板，但模板对预处理、聚类算法等敏感，导致可重复性差。本文从拓扑几何视角重新审视，将模板视为嵌入全局状态空间结构的地标，保留了极性作为有意义的几何关系而非冗余。实验表明，地标基础的状态定义在捕捉状态结构和分析性能上优于传统模板。该方法为状态定义提供了更稳定、更原则性的基础，有利于跨研究比较。
source: biorxiv
selection_source: fresh_fetch
motivation: 传统微状态分析模板依赖性导致可重复性差，需要更稳定、基于全局结构的状态定义方法。
method: 从拓扑几何视角，将微状态模板重新定义为嵌入全局状态空间结构的地标，保留极性作为几何关系。
result: 地标基础的状态定义在捕捉状态结构上优于传统模板，提高了分析性能。
conclusion: 核心问题在于如何定义有效节点而不丢弃拓扑关系，地标方法为状态定义提供了更原则性基础。
---

## 摘要
状态转移方法，包括脑电图微状态分析及相关功能磁共振成像方法如隐马尔可夫模型和共激活模式分析，提供了将神经动力学粗粒化为少量准稳定态的广泛使用工具。其效用已在静息态和任务范式得到验证，应用范围从认知神经科学到精神与神经疾病的候选生物标志物。然而，一个基本限制依然存在：几乎所有下游时间测量都依赖于初始定义的模板图谱。在传统流程中，模板源自全局场功率峰值处电压图的极性不变聚类，使得最终状态定义对预处理、采样、初始化、聚类算法及聚类数选择敏感。因此，该方法捕捉了EEG动力学中的粗粒度规律，而对产生这些状态的更大几何组织约束较弱。这种模板依赖性对可重复性以及跨研究和EEG电极帽的比较构成重大挑战。本文从拓扑-几何角度重新审视这一问题。我们不将模板视为从GFP峰值图谱提取的聚类中心，而是将其作为嵌入于由头皮电压图相互相似性构建的状态空间全局结构中的地标。在此表述中，微状态模板被重新发现为组织连续神经状态拓扑的主导轴的离散代表。这种重新表述保留了极性作为一种有意义的几何关系，而非将其视为分析冗余而预先消除。它还将注意力从孤立的状态标签转向状态空间本身的地形：使局部状态变得可解释的更广泛关系结构。使用该方法，我们表明基于地标的状态定义在捕捉状态结构和提升分析性能方面优于传统模板。这些发现表明，EEG微状态分析的核心问题比聚类优化更广泛：它涉及如何定义用于粗粒化连续动力学的有效节点，同时不丢弃组织它们的拓扑。通过将微状态分析的概念基础从模板转向地标，本文方法为状态定义提供了更原则性且可能更稳定的基础，包括在fMRI中。这种拓扑-几何重新评估拓展了传统微状态分析，并为跨数据集、范式和记录系统的更统一比较开辟了路径。

## Abstract
State-transition approaches, including EEG microstate analysis and related fMRI methods such as hidden Markov models (HMMs) and co-activation pattern (CAP) analysis, provide widely used tools for coarse-graining neural dynamics into a small set of quasi-stable states. Its utility has been demonstrated across resting-state and task paradigms, with broad applications ranging from cognitive neuroscience to candidate biomarkers for psychiatric and neurological disorders. A fundamental limitation remains, however: nearly all downstream temporal measures are conditional on the template maps defined at the outset. In the conventional pipeline, templates are derived from polarity-invariant clustering of voltage maps at global field power (GFP) peaks, making the resulting state definitions sensitive to preprocessing, sampling, initialization, clustering algorithms, and the choice of cluster number. Consequently, the method captures coarse regularities in EEG dynamics, while only weakly constraining the larger geometric organization from which those states emerge. This template dependence poses a major challenge for reproducibility and for comparisons across studies and EEG caps. Here, we revisit this problem from a topological-geometric perspective. We treat templates not as cluster centroids extracted from GFP-peak maps, but as landmarks embedded in the global structure of a state space constructed from mutual similarities among scalp voltage maps. In this formulation, microstate templates are rediscovered as discrete representatives of dominant axes that organize continuous neural-state topography. This reformulation preserves polarity as a meaningful geometric relation instead of eliminating it at the outset as analytical redundancy. It also shifts attention from isolated state labels to the terrain of the state space itself: the broader relational structure within which local states become interpretable. Using this approach, we show that landmark-based state definitions outperform conventional templates in capturing state structure and improving analytical performance. These findings suggest that the central problem in EEG microstate analysis is broader than clustering optimization: it concerns how to define valid nodes for coarse-graining continuous dynamics without discarding the topology that organizes them. By shifting the conceptual basis of microstate analysis from templates to landmarks, the present approach provides a more principled and potentially more stable foundation for state definition, including in fMRI. This topolo-geometric reappraisal extends conventional microstate analysis and opens a path toward more unified comparisons across datasets, paradigms, and recording systems.