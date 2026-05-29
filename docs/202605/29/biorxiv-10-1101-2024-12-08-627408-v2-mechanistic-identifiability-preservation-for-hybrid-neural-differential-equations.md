---
title: Mechanistic Identifiability Preservation for Hybrid Neural Differential Equations
title_zh: 混合神经常微分方程的机械可辨识性保持
authors: "Whipple, B., Hernandez-Vargas, E. A."
date: 2026-05-23
pdf: "https://www.biorxiv.org/content/10.1101/2024.12.08.627408v2.full.pdf"
tags: ["query:neural-ode"]
score: 8.0
evidence: 混合神经ODE的理论框架，可应用于医学图像分析
tldr: 在生物学和工程学领域的混合神经微分方程(HNDEs)应用中，将神经网络嵌入机械模型提升拟合能力，但神经校正可能引入观测简并性，损害机械参数的可识别性和科学可解释性。本文通过形式化有界神经校正类并推导Gronwall型轨迹与观测差异界限，建立了神经扰动幅度与参数模糊性之间的定量联系，并证明了在明确可量化容忍度内保持近似参数可恢复性的充分条件。在基准系统上的似然剖面分析证实，神经增强系统性地削弱机械可识别性但未完全消除，揭示了模型表达性与可识别性之间的根本权衡。该研究为在科学智能计算中安全有效地部署HNDEs提供了理论基础和可行指导。
source: biorxiv
selection_source: fresh_fetch
motivation: 混合神经微分方程中神经校正可能引入观测简并性，需理论框架以保持机械参数的可识别性和科学可解释性。
method: 形式化有界神经校正类，推导Gronwall型轨迹与观测差异界限，建立神经扰动与参数模糊性之间的定量联系。
result: 神经增强系统性地削弱但未消除机械可识别性，在容忍度内可保持近似参数可恢复性，存在表达性-可识别性权衡。
conclusion: 为在科学智能计算中部署HNDEs提供理论基础，指导可识别性保持。
---

## 摘要
混合神经常微分方程将神经网络组件嵌入机械支架中，结合了领域驱动模型的结构可解释性与神经动力学的近似能力。尽管它们在生物学和工程学中的应用日益增多，但神经增强可能引入观测退化，从而损害机械可辨识性和科学可解释性。

在本文中，我们开发了一个用于实际保持混合神经常微分方程中机械可辨识性的理论框架。我们形式化了有界神经校正类，并推导了将神经扰动与机械参数模糊性联系起来的Gronwall型轨迹和观测差异界限。我们进一步建立了充分条件，在这些条件下，混合神经校正能在显式可量化的容差内保持近似的机械参数可恢复性。

对基准系统的经验似然分布分析证实，神经增强系统地削弱——但并未消除——机械可辨识性，揭示了一种基本的表达性-可辨识性权衡。这些结果为在科学智能计算中部署混合神经常微分方程提供了理论基础和可行指导。

## Abstract
Hybrid neural differential equations (HNDEs) embed neural network components within mechanistic scaffolds, combining the structural interpretability of domain-derived models with the approximation power of neural dynamics. Despite their growing adoption in biology and engineering, neural augmentation can introduce observational degeneracies that compromise mechanistic identifiability and scientific interpretability.

In this paper, we develop a theoretical framework for practical preservation of mechanistic identifiability in HNDEs. We formalize bounded neural correction classes and derive Gronwall-type trajectory and observational discrepancy bounds linking neural perturbations to mechanistic parameter ambiguity. We further establish sufficient conditions under which hybrid neural corrections preserve approximate mechanistic parameter recoverability up to explicitly quantifiable tolerances.

Empirical likelihood profile analyses on benchmark systems confirm that neural augmentation systematically weakens--but does not eliminate--mechanistic identifiability, revealing a fundamental expressiveness-identifiability trade-off. These results provide theoretical foundations and actionable guidance for deploying HNDEs in scientific intelligent computing.