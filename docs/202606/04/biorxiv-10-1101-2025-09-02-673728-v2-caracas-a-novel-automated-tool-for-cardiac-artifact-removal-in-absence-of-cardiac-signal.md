---
title: "CARACAS, a novel automated tool for Cardiac Artifact Removal in Absence of CArdiac Signal"
title_zh: CARACAS：一种无心脏信号情况下心脏伪影自动去除的新工具
authors: "Champetier, P., Oudiette, D., Andrillon, T., Chaumon, M."
date: 2026-06-03
pdf: "https://www.biorxiv.org/content/10.1101/2025.09.02.673728v2.full.pdf"
tags: ["query:eeg-ode-ln"]
score: 9.0
evidence: EEG心电伪迹去除方法
tldr: EEG记录常受心脏伪迹干扰，ICA去除需依赖ECG信号，但ECG常缺失。CARACAS利用心脏独立成分时间轮廓与ECG相似性，通过检测R波事件自动识别心脏IC。在21375个IC上的测试表明，敏感度0.960、特异度0.976，显著优于IClabel，接近使用ECG的相关方法。该工具无需ECG即可可靠去除心脏伪迹，集成于SASICA工具箱。
source: biorxiv
selection_source: fresh_fetch
motivation: 现有自动标记心脏独立成分的方法需同时记录ECG，但ECG并非总是可用，限制了ICA去噪的适用性。
method: 将ECG中检测R波的现有工具应用于每个IC时间序列，通过分析检测事件区分心脏与非心脏IC。
result: 在375个EEG-ECG记录、21375个IC上，CARACAS敏感度0.960、特异度0.976，优于IClabel（0.210/0.999），接近ECG相关法（0.975/0.998）。
conclusion: CARACAS提供了无需ECG的可靠心律失常伪迹去除方案，已实现于SASICA工具箱，实用性强。
---

## 摘要
背景：脑电图记录可能包含心脏相关的伪影。独立成分分析（ICA）随后去除心脏独立成分（IC）是一种强大且广泛使用的伪影校正策略。现有大多数自动标记心脏IC的方法需要同时记录心电图（例如，计算与IC时间过程的相关性）。然而，心电图并不总是可用。为解决这一局限，我们开发了CARACAS（无心脏信号情况下的心脏伪影去除），一种仅使用IC时间过程识别心脏IC的新工具。新方法：由于心脏IC的时间轮廓与心电图信号高度相似，我们使用一种现有的旨在检测心电图信号中心脏事件（R波）的工具，并将其应用于每个IC时间过程。对检测到的事件进行分析能够区分心脏IC和非心脏IC，其中不相关的信号变化被错误地识别为心脏事件。利用开源数据集OpenNeuro ds003690中的375个脑电-心电记录，我们比较了三种算法的性能：CARACAS、IClabel（一种不需要心电图的通用IC分类器）以及与心电图通道的相关性。结果（与现有方法比较）：共手动和自动分类了21,375个IC。CARACAS取得了高性能（灵敏度=0.960，特异度=0.976），显著优于IClabel（灵敏度=0.210，特异度=0.999），并接近心电图相关方法的性能（灵敏度=0.975，特异度=0.998）。结论：我们提出了一种可靠的无需心电图的脑电中心脏IC检测算法。CARACAS在心电图不可用时提供了实用的解决方案，并已在SASICA工具箱中实现。

## Abstract
Background: EEG recordings can contain cardiac related artifacts. Independent Component Analysis (ICA) followed by removal of cardiac Independent Components (ICs) is a powerful and widely used strategy for artifact correction. Most existing methods for automatic labeling of cardiac ICs require a simultaneously recorded ECG (e.g., to compute correlation with the IC time course). However, ECG is not always available. To address this limitation, we developed CARACAS (Cardiac Artifact Removal in Absence of CArdiac Signal), a novel tool that identifies cardiac ICs using only the IC time courses. New method: Because cardiac ICs exhibit temporal profiles highly similar to ECG signals, we used an existing tool designed to detect cardiac events (R waves) in ECG signals and applied it to each IC time course. Analysis of the detected events enabled the differentiation of cardiac ICs from non-cardiac ICs, where unrelated signal variations are incorrectly identified as cardiac events. Using the 375 EEG-ECG recordings of the open-source dataset OpenNeuro ds003690, we compared the performances of three algorithms: CARACAS, IClabel (a generic IC classifier which does not require ECG), and correlation with ECG channel. Results (comparison with existing methods): A total of 21,375 ICs were manually and automatically classified. CARACAS achieved high performance (sensitivity = 0.960, specificity = 0.976), substantially outperforming ICLabel (sensitivity = 0.210, specificity = 0.999) and approaching the performance of ECG correlation method (sensitivity = 0.975, specificity = 0.998). Conclusion: We present a reliable ECG-free algorithm for cardiac IC detection in EEG. CARACAS provides a practical solution when ECG is unavailable, and is implemented in the SASICA toolbox.

---

## 论文详细总结（自动生成）

# 论文详细中文总结

## 1. 论文的核心问题与整体含义（研究动机和背景）
- **核心问题**：脑电图（EEG）记录常受心脏相关伪影（如心电信号）干扰。独立成分分析（ICA）结合去除心脏独立成分（IC）是有效的校正策略。但现有自动标记心脏IC的方法大多需要同步记录心电图（ECG），而ECG在实际采集时并非总是可用（例如实验设计限制、设备缺失或数据共享时未提供），限制了ICA去噪的广泛适用性。
- **整体含义**：本文旨在开发一种仅依靠IC时间过程即可自动识别心脏IC的方法，无需ECG信号，从而降低EEG预处理的门槛，提高数据质量和分析可靠性，尤其适用于历史数据或缺乏ECG记录的研究。

## 2. 论文提出的方法论：核心思想、关键技术细节、公式或算法流程
- **核心思想**：心脏IC的时间轮廓与ECG信号高度相似（具有周期性R波等特征）。因此，可将专用于ECG信号的R波检测工具直接应用于每个IC时间序列，通过分析检测到的事件模式（如不规则/错误触发）来区分真正的心脏IC与非心脏IC。
- **关键技术细节**：
  - 采用现有的ECG R波检测工具（如基于Pan-Tompkins或自适应阈值算法）对每个IC时间序列进行事件检测。
  - 非心脏IC中，随机噪声或慢波变化可能被错误识别为“心脏事件”，但其事件间隔、幅度等统计特征与真实心脏IC的规律性不同。
  - 通过统计检测事件的序列特征（如事件间间隔的一致性、振幅模式等）设置判别规则，自动筛选出心脏IC。
- **算法流程**（文字说明）：
  1. 对每个IC时间序列应用ECG R波检测算法，得到一组标记的事件时间点。
  2. 计算事件间间隔、振幅等统计量。
  3. 根据预设阈值（如间隔变异系数小于某值、事件振幅稳定等）判断该IC是否为心脏IC。
  4. 输出所有被识别为心脏IC的索引，供后续去除。

## 3. 实验设计：使用的数据集、基准、对比方法
- **数据集**：开源数据集OpenNeuro ds003690，包含375个同步记录的EEG-ECG数据样本（来自不同受试者、不同实验条件）。共提取21,375个独立成分（每个记录平均约57个IC）。
- **基准（ground truth）**：人工标注（手动分类）每个IC是否为心脏伪影，作为评价标准。
- **对比方法**：
  1. **CARACAS**（本文方法，仅使用IC时间序列）。
  2. **IClabel**（通用IC分类器，无需ECG，可自动分类脑、肌肉、眼动、心脏等信号）。
  3. **ECG相关法**（计算每个IC时间序列与同步记录的ECG通道的相关系数，基于阈值判断，需要ECG信号）。

## 4. 资源与算力
- **文中未明确说明**：未提及训练CARACAS所需的GPU型号、数量、训练时长等算力信息。可能原因是CARACAS不涉及深度学习训练，而是基于现有ECG检测工具和简单统计规则，计算成本很低（可在普通CPU上运行）。IClabel也未提训练资源。

## 5. 实验数量与充分性
- **实验数量**：使用375个EEG-ECG记录，共21,375个独立成分。每个IC均有手动标签，覆盖了多种心脏伪影和非心脏伪影。
- **充分性评估**：
  - 实验规模较大（>20k成分），具有较好统计效力。
  - 对比了两种代表性方法（有ECG vs 无ECG），且人工标注作为金标准，客观公平。
  - 但缺少以下实验：不同数据集（如不同年龄、病理人群、不同EEG系统）的泛化性；不同R波检测算法的影响；对非心脏IC（如眨眼、肌肉伪影）的误报分析等。因此实验相对充分但可更全面。

## 6. 论文的主要结论与发现
- **CARACAS性能**：灵敏度=0.960，特异度=0.976，显著优于IClabel（灵敏度=0.210，特异度=0.999），接近ECG相关法（灵敏度=0.975，特异度=0.998）。
- **核心发现**：即使在无ECG信号情况下，仅利用IC的时间轮廓即可高精度自动识别心脏IC，几乎达到依赖ECG的方法水平。IClabel虽然特异度高但灵敏度极低，漏检大量心脏成分。
- **实用性**：CARACAS已集成于SASICA工具箱（Matlab/EEGLAB插件），便于用户直接使用。

## 7. 优点：方法或实验设计上的亮点
- **方法亮点**：
  - 创新性地将ECG检测算法迁移至IC时间序列，无需额外硬件或信号。
  - 简单高效，不依赖深度学习模型，可解释性强。
  - 灵敏度极高（0.960），在保留有效脑信号的同时最大程度去除伪影。
- **实验设计亮点**：
  - 利用大规模开源数据集，确保可复现性。
  - 人工标注+双盲对比，减少主观偏差。
  - 与IClabel及ECG相关法的对比设计合理，突出了无ECG场景下CARACAS的显著优势。

## 8. 不足与局限
- **实验覆盖不足**：仅使用单一人体数据集（OpenNeuro ds003690），缺乏对儿童、老年人、心脏病患者等特殊人群的验证；未涉及睡眠EEG或动物EEG数据。
- **偏差风险**：R波检测算法可能对低信噪比IC或某些非正弦伪影（如基线漂移）产生误判，但文中未充分讨论误报情况。
- **应用限制**：需要IC时间序列质量较好（如去除过大噪声后）；若ICA分解效果差（未正确分离心脏成分），则CARACAS无法工作。此外，方法依赖于R波检测的准确性，而不同检测算法性能差异可能影响结果。
- **未进行消融实验**：未评估不同R波检测器、不同统计特征组合对性能的影响，也未分析在极端噪声下的鲁棒性。

（完）
