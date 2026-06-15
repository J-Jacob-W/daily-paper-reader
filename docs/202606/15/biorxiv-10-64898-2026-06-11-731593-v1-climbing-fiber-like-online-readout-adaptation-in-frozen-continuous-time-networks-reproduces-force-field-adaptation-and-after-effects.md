---
title: Climbing-fiber-like online readout adaptation in frozen continuous-time networks reproduces force-field adaptation and after-effects
title_zh: 冻结连续时间网络中攀爬纤维样的在线读出适应复制了力场适应与后效
authors: "Kobayashi, J."
date: 2026-06-15
pdf: "https://www.biorxiv.org/content/10.64898/2026.06.11.731593v1.full.pdf"
tags: ["query:neural-ode"]
score: 6.0
evidence: 使用液态神经网络（CfC）实现在线自适应，可迁移至医学影像
tldr: 离线训练的连续时间网络（如CfC）缺乏在线校准机制。本文冻结CfC核心，仅通过爬行纤维样误差信号自适应线性读出（LMS/RLS规则）。在平面两杆到达任务中，该方法能纠正涡旋力场扰动，去除后产生镜像后效，且对场强和方向鲁棒。结果表明，只适应读出即可提供生物启发、低成本的在线误差适应层。
source: biorxiv
selection_source: fresh_fetch
motivation: 离线训练的连续时间网络缺乏在线适应机制，需解决植物动力学变化时的校准问题。
method: 冻结CfC核心，仅在线自适应线性读出，使用爬行纤维样误差信号和最小均方规则。
result: 在涡旋力场中纠正扰动，去除后产生镜像后效，且适应效果对场强度和方向鲁棒。
conclusion: 只适应读出提供了生物启发、低成本的在线误差适应层，无需修改核心。
---

## 摘要
基于液态神经网络及相关连续时间模型（如LTC和CfC）的机器人运动控制通常通过时间反向传播进行离线训练，且缺乏在植物动力学变化时进行在线重新校准的显式机制。我们探究一个冻结的CfC核心（其液态状态跨越一个固定的连续时间基）是否可以通过仅使用攀爬纤维样的误差信号对其线性读出进行适应来支持小脑风格的在线适应。在具有速度依赖卷曲力场的平面双连杆到达模拟中，我们使用最小均方（LMS）规则下的反馈误差学习（FEL）信号在线调整读出，保持核心不变。冻结核心仅读出控制器能够矫正受卷曲扰动的手臂到达，并在力场移除后产生镜像后效——内模型学习的标志——而仅反馈控制器无法产生此效果。当使用循环状态（而非投影的运动输出）作为读出基础时，该结果从密集的CfC泛化到稀疏的神经电路策略（NCP）布线；它对力场强度和方向具有鲁棒性；递归最小二乘变体适应更快但去适应缓慢，因为其协方差崩溃，而协方差重置的安全遗忘规则可消除这种刚性。在所探索的双连杆平面模拟范围内，我们没有发现需要适应冻结核心的容量限制。因此，在这项模拟研究中，仅适应读出可为离线训练的连续时间控制器提供一种生物启发、低成本的在线误差适应层。

## Abstract
Robotic motor control built on liquid neural networks and related continuous-time models, such as LTC and CfC, is typically trained offline via backpropagation through time and lacks an explicit mechanism for recalibrating online as plant dynamics change. We ask whether a frozen CfC core, whose liquid state spans a fixed continuous-time basis, can support cerebellar-style online adaptation by adapting only its linear readout with a climbing-fiber-like error signal. In a planar two-link reaching simulation with a velocity-dependent curl force field, we adapt the readout online with a feedback-error-learning (FEL) signal under a least-mean-squares (LMS) rule, leaving the core untouched. The frozen-core readout-only controller re-straightens curl-perturbed reaches and, upon field removal, produces a mirror-image after-effect---the signature of internal-model learning---that a feedback-only controller does not produce. The result generalizes from a dense CfC to a sparse Neural-Circuit-Policy (NCP) wiring when the recurrent state, rather than the projected motor output, is used as the readout basis; it is robust to force-field strength and direction; and a recursive-least-squares variant adapts faster but de-adapts slowly because its covariance collapses, a rigidity that a covariance-reset safe-forgetting rule removes. Within the explored two-link planar simulation range, we did not find a capacity limit that would require adapting the frozen core in the tested conditions. In this simulation study, adapting only the readout therefore provides a biologically inspired, low-cost online error-adaptation layer for offline-trained continuous-time controllers.