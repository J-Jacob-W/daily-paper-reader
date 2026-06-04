---
title: "Quilting the Brain: Whole-Brain iEEG Reconstruction via Incomplete Observation Linear Mixed Models"
title_zh: 拼接大脑：通过不完全观测线性混合模型进行全脑iEEG重建
authors: "Wang, Y., Li, M., Bringas Vega, M. L., Valdes-Sosa, P. A."
date: 2026-06-03
pdf: "https://www.biorxiv.org/content/10.64898/2026.05.31.729074v1.full.pdf"
tags: ["query:eeg-ode-ln"]
score: 7.0
evidence: 颅内脑电图全脑重建方法用于神经解码
tldr: 颅内脑电图（iEEG）因临床植入限制只能记录分散的局部活动，导致全脑重建困难。本文提出不完全观测线性混合效应模型（IOLMM），结合Sure Independence Screening（SIS）区分真实信号与容积传导伪影，并通过层次化模型分离群体与个体效应。在106名患者的MNI Open iEEG Atlas上成功重建睡眠阶段皮质源功率图，恢复NREM慢波活动的前额优势等已知特征。该工作建立了首个基于iEEG的皮质表面标准电生理图谱，为癫痫病灶检测和系统神经科学提供定量参考。
source: biorxiv
selection_source: fresh_fetch
motivation: iEEG临床植入导致观测碎片化，无法获得全脑连续活动图，阻碍群体分析与标准化研究。
method: 提出IOLMM框架，使用SIS筛选真实源，通过层次混合模型解耦群体固定与个体随机效应，解决尺度模糊。
result: 在MNI Open iEEG Atlas上重建睡眠阶段皮质源功率图，验证NREM慢波前额优势等电生理层级。
conclusion: 首次建立基于iEEG的皮质表面标准电生理图谱，为脑功能研究与癫痫病灶检测提供定量基准。
---

## 摘要
以高时空分辨率绘制人脑功能受到非侵入性成像的物理限制和侵入性电生理稀疏采样的制约。虽然颅内脑电图（iEEG）能以毫米级精度捕捉局部场电位，但临床植入策略导致“覆盖悖论”：观测局限于不相交的、患者特定的斑块，导致大部分皮层未被观测。本研究引入了不完全观测线性混合效应模型（IOLMM），这是一种统计框架，通过将碎片化观测“拼接”成连续的、全脑源活动图来解决这一悖论。我们的方法整合了两项创新：（1）从超高维统计中改编的确定独立筛选（SIS），用于区分真实生理信号与容积传导的“鬼源”；（2）分层IOLMM，将组级生理固定效应与受试者特异性工具随机效应解耦，解决了困扰iEEG组分析的缩放模糊性。应用于MNI开放iEEG图谱，通过跨清醒、N2、N3和REM状态的睡眠阶段依赖性皮层源功率重建验证了该框架，恢复了NREM慢波活动的前额优势以及来自106名患者碎片化记录的渐进式电生理层级。这项工作建立了首个源自iEEG的皮层表面级规范电生理图谱，为检测和预测致痫灶提供了定量参考，并弥合了电生理微观精度与系统神经科学宏观范围之间的差距。

## Abstract
Mapping human brain function at high spatiotemporal resolution is constrained by the physical limitations of non-invasive imaging and the sparse sampling of invasive electrophysiology. While intracranial electroencephalography (iEEG) captures local field potentials with millimeter precision, clinical implantation strategies result in a ``coverage paradox'': observations are restricted to disjoint, patient-specific patches, leaving most of the cortex unobserved. This study introduces the Incomplete Observation Linear Mixed-Effect Model (IOLMM), a statistical framework that resolves this paradox by ``quilting'' fragmented observations into continuous, whole-brain source activity maps. Our approach integrates two innovations: (1) Sure Independence Screening (SIS) adapted from ultra-high-dimensional statistics to distinguish true physiological signals from volume-conducted ``ghost sources''; (2) a hierarchical IOLMM that decouples group-level physiological fixed effects from subject-specific instrumental random effects, solving the scaling ambiguities that plague iEEG group analyses. Applied to the MNI Open iEEG Atlas, the framework is validated through sleep stage-dependent cortical source power reconstruction across Wake, N2, N3, and REM states, recovering the frontal predominance of NREM slow-wave activity and the graded electrophysiological hierarchy from fragmented recordings of 106 patients. This work establishes the first cortical surface-level normative electrophysiological atlas derived from iEEG, providing a quantitative reference for detecting and predicting epileptogenic lesions and bridging the gap between the microscopic precision of electrophysiology and the macroscopic scope of systems neuroscience.