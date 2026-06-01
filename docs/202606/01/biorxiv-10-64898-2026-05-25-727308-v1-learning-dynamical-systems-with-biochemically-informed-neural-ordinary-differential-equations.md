---
title: Learning dynamical systems with biochemically informed neural ordinary differential equations
title_zh: 利用生物化学信息神经常微分方程学习动力系统
authors: "Fonseca, L. L., Laubenbacher, R., Boettcher, L."
date: 2026-05-28
pdf: "https://www.biorxiv.org/content/10.64898/2026.05.25.727308v1.full.pdf"
tags: ["query:neural-ode"]
score: 7.0
evidence: 神经常微分方程应用于生化动力系统
tldr: 生化反应动力系统建模面临过程函数形式未知的难题。本文提出BINODEs，保留化学计量结构，用神经网络表示各过程，并融入过程输入、符号约束等先验知识。在Monod、Lotka-Volterra等模型上，该方法能准确恢复系统轨迹和过程级结构。BINODEs在机械论可解释性与数据驱动灵活性之间实现了有效折中。
source: biorxiv
selection_source: fresh_fetch
motivation: 生化反应动力系统中过程函数形式未知，传统建模难以从数据推断，需要兼顾结构可解释性和灵活性。
method: 提出BINODEs，将化学计量矩阵与神经网络过程相结合，通过线性层映射状态导数，并嵌入生物学先验如符号约束和单调性。
result: 在Monod、Lotka-Volterra、药代动力学和超日节律内分泌模型中，BINODEs成功恢复了轨迹和过程级结构。
conclusion: BINODEs为部分已知的生化动力系统提供了一种兼顾可解释性与灵活性的建模方法。
---

## 摘要
生物化学反应的常微分方程模型通常被表述为化学计量系统，其中动力学源于一系列相互作用的进程。一个核心挑战是，每个进程的函数形式很少先验已知，且可能难以从数据中推断。我们提出了生物化学信息神经常微分方程（BINODEs），这是一种神经ODE框架，保留机制模型的化学计量结构，同时通过神经网络表示各个进程。在BINODEs中，神经网络进程（NNPs）的输出通过一个类似于化学计量矩阵的线性层映射到状态导数。这种架构允许直接将生物学辅助信息（如进程特定输入、符号约束和单调性假设）构建到模型中。我们描述了NNPs对几种标准生化速率定律的逼近性质，并表明所提出的框架在Monod、Lotka-Volterra、药代动力学和超日内分泌模型中恢复了轨迹和进程级结构。这些结果表明，BINODEs在建模部分已知的生化或生物动力系统时，在机制可解释性和数据驱动灵活性之间提供了有用的折衷。

## Abstract
Ordinary differential equation models of biochemical reactions are often formulated as stoichiometric systems in which the dynamics arise from a collection of interacting processes. A central challenge is that the functional form of each process is rarely known a priori and may be difficult to infer from data. We propose biochemically informed neural ordinary differential equations (BINODEs), a neural-ODE framework that retains the stoichiometric structure of mechanistic models while representing individual processes by neural networks. In BINODEs, the outputs of neural network processes (NNPs) are mapped to state derivatives through a linear layer analogous to a stoichiometric matrix. This architecture allows biological side information, such as process-specific inputs, sign constraints, and monotonicity assumptions, to be built directly into the model. We characterize the approximation properties of NNPs for several standard biochemical rate laws and show that the proposed framework recovers both trajectories and process-level structure in Monod, Lotka-Volterra, pharmacokinetic, and ultradian endocrine models. These results suggest that BINODEs offer a useful compromise between mechanistic interpretability and data-driven flexibility for modeling partially known biochemical or biological dynamical systems.