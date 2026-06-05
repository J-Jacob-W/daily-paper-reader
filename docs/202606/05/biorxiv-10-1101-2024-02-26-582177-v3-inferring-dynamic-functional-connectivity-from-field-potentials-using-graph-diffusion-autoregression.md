---
title: Inferring Dynamic Functional Connectivity from Field Potentials Using Graph Diffusion Autoregression
title_zh: 使用图扩散自回归从场电位推断动态功能连接
authors: "Schwock, F., Bloch, J., Khateeb, K., Zhou, J., Atlas, L., Yazdan-Shahmorad, A."
date: 2026-05-29
pdf: "https://www.biorxiv.org/content/10.1101/2024.02.26.582177v3.full.pdf"
tags: ["query:eeg-ode-ln"]
score: 6.0
evidence: 利用图扩散从场电位估计动态功能连接
tldr: 现有动态功能连接估计多忽略结构信息且静态。提出图扩散自回归(GDAR)模型，在结构连接图上施加网络约束和扩散约束的线性自回归，推断高动态功能连接。在模拟数据和猕猴皮层记录中验证，成功捕捉光遗传刺激、中风后变化及行为相关的快速动态。该方法结合结构信息，提升对快速神经过程的理解。
source: biorxiv
selection_source: fresh_fetch
motivation: 现有动态功能连接估计多忽略结构信息且静态，无法捕捉快速神经动态。
method: 提出图扩散自回归(GDAR)模型，在结构连接图上施加网络约束和扩散约束的线性自回归。
result: 在模拟数据和猕猴感觉运动皮层记录中，模型成功描述光遗传刺激、中风后dFC变化及行为相关动态。
conclusion: GDAR模型能有效结合结构信息推断高动态功能连接，揭示快速神经通信。
---

## 摘要
估计动态功能连接（dFC）正受到越来越多的关注，这得益于多部位神经记录技术的快速发展以及更好地理解认知过程的努力。然而，大多数研究关注的是功能连接的静态估计，无法捕捉高度动态的神经过程，同时也忽略了关于大脑结构组织的信息。为了解决这些问题，我们引入了一类网络约束的线性自回归模型，该模型在预定义的结构连接图的边上产生了高度动态的功能连接信号。此外，我们证明添加额外的扩散约束可以提高模型性能。我们在模拟神经活动以及放置在猕猴感觉运动皮层的硬膜下和皮层内微电极阵列记录中成功验证了所得到的图扩散自回归（GDAR）模型，证明了它能够描述由光遗传刺激引起的快速通信动态、中风和电刺激后静息状态dFC的变化，以及在伸手任务中行为的神经相关性。

## Abstract
Estimating dynamic functional connectivity (dFC) is attracting increased attention, spurred by rapid advancements in multi-site neural recording technologies and efforts to better understand cognitive processes. Yet, most studies focus on static estimates of functional connectivity that cannot capture highly dynamic neural processes, while also ignoring information about the structural organization of the brain. To address these issues, we introduce a class of network-constrained linear autoregressive models that give rise to a highly dynamic functional connectivity signal on the edges of a predefined structural connectivity graph. Furthermore, we demonstrate that adding an additional diffusion constraint improves the models performance. We successfully validated the resulting graph diffusion autoregressive (GDAR) model on simulated neural activity and recordings from subdural and intracortical micro-electrode arrays placed in macaque sensorimotor cortex demonstrating its ability to describe rapid communication dynamics induced by optogenetic stimulation, changes in resting state dFC following stroke and electrical stimulation, and neural correlates of behavior during a reach task.