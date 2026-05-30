---
title: Mechanistic Identifiability Preservation for Hybrid Neural Differential Equations
title_zh: 混合神经常微分方程的机制可辨识性保持
authors: "Whipple, B., Hernandez-Vargas, E. A."
date: 2026-05-23
pdf: "https://www.biorxiv.org/content/10.1101/2024.12.08.627408v2.full.pdf"
tags: ["query:neural-ode"]
score: 8.0
evidence: 混合神经微分方程理论可用于医学成像分析
tldr: 混合神经常微分方程结合机理模型与神经网络，但神经增强可能破坏机理参数的可辨识性。本文提出有界神经校正类理论，推导轨迹与观测差异界限，并给出保持近似可辨识性的充分条件。实验表明神经增强系统性地削弱可辨识性，揭示表达力与可辨识性的内在权衡。该工作为科学智能计算中部署HNDEs提供理论依据与实用指导。
source: biorxiv
selection_source: fresh_fetch
motivation: 解决HNDEs中神经增强导致机理参数观测退化、损害科学可解释性的问题。
method: 形式化有界神经校正类，导出Gronwall型轨迹与观测差异界，建立保证近似参数可恢复性的充分条件。
result: 实验确认神经增强削弱但未消除机理可辨识性，发现表达力与可辨识性之间存在系统权衡。
conclusion: 为HNDEs在科学智能计算中的部署提供理论基础和可操作指南，助力模型可解释性。
---

## 摘要
混合神经常微分方程将神经网络组件嵌入到机制框架中，结合了领域推导模型的结构可解释性与神经动力学的逼近能力。尽管它们在生物学和工程中的应用日益增多，神经增强可能引入观测退化，从而损害机制可辨识性和科学可解释性。

在本文中，我们为混合神经常微分方程中机制可辨识性的实际保持建立了一个理论框架。我们形式化了有界神经校正类，并推导了Gronwall型轨迹和观测差异界，将神经扰动与机制参数模糊性联系起来。我们进一步建立了充分条件，在这些条件下，混合神经校正能够在明确可量化的容差内保持近似的机制参数可恢复性。

在基准系统上的经验似然谱分析证实，神经增强系统地削弱了——但并未消除——机制可辨识性，揭示了表达性与可辨识性之间的基本权衡。这些结果为在科学智能计算中部署混合神经常微分方程提供了理论基础和可操作指南。

## Abstract
Hybrid neural differential equations (HNDEs) embed neural network components within mechanistic scaffolds, combining the structural interpretability of domain-derived models with the approximation power of neural dynamics. Despite their growing adoption in biology and engineering, neural augmentation can introduce observational degeneracies that compromise mechanistic identifiability and scientific interpretability.

In this paper, we develop a theoretical framework for practical preservation of mechanistic identifiability in HNDEs. We formalize bounded neural correction classes and derive Gronwall-type trajectory and observational discrepancy bounds linking neural perturbations to mechanistic parameter ambiguity. We further establish sufficient conditions under which hybrid neural corrections preserve approximate mechanistic parameter recoverability up to explicitly quantifiable tolerances.

Empirical likelihood profile analyses on benchmark systems confirm that neural augmentation systematically weakens--but does not eliminate--mechanistic identifiability, revealing a fundamental expressiveness-identifiability trade-off. These results provide theoretical foundations and actionable guidance for deploying HNDEs in scientific intelligent computing.