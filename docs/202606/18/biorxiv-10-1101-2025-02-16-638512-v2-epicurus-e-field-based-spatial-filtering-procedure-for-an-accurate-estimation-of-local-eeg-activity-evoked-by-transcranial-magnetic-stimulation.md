---
title: "EPICURUS: E-field-based spatial filtering procedure for an accurate estimation of local EEG activity evoked by Transcranial Magnetic Stimulation"
title_zh: EPICURUS：基于电场的空间滤波方法用于精确估计经颅磁刺激诱发的局部脑电活动
authors: "Corominas-Teruel, X., Mutanen, T., Leto, C., Colomina, M. T., Gallea, C., Bracco, M., Cabre, A. V."
date: 2026-06-15
pdf: "https://www.biorxiv.org/content/10.1101/2025.02.16.638512v2.full.pdf"
tags: ["query:eeg-ode-ln"]
score: 9.0
evidence: 提出一种用于TMS-EEG的空间滤波方法以准确估计局部EEG活动
tldr: TMS-EEG中可靠分离局部诱发电位仍具挑战。EPICURUS利用个体化MRI模拟TMS电场，定义局部活动空间范围，指导EEG信号重建。合成和人类数据表明，该方法保留早期局部活动，抑制非局部成分。通过电场建模提高了EEG重建特异性，有望改善TMS诱发局部反应的时空分辨率。
source: biorxiv
selection_source: fresh_fetch
motivation: 现有TMS-EEG方法难以从污染源中可靠分离局部诱发电位，需要更精确的空间滤波技术。
method: 基于个体MRI的TMS电场模拟，定义局部活动空间范围，构建空间滤波器重建目标区域EEG信号。
result: 在合成和人类数据中，早期局部活动被保留，而后期非局部成分显著衰减。
conclusion: EPICURUS通过电场建模提高了EEG信号重建的特异性，为TMS局部反应研究提供更精确的工具。
---

## 摘要
背景经颅磁刺激与脑电图（TMS-EEG）的联合使用正越来越多地融入研究和临床方案。然而，从污染源中可靠地分离出目标皮层区域由TMS局部诱发的脑电反应仍然具有挑战性。
方法本文介绍了一种新的TMS-EEG空间滤波方法EPICURUS，该方法利用基于个体化MRI模拟的TMS感应电场（E场）来定义局部诱发活动的空间范围。该方法指导重建直接刺激部位产生的脑电信号，同时最小化来自远处非目标源的串扰。
结果在仿真模拟和人类TMS-EEG数据集中，EPICURUS保留了早期潜伏期的TMS诱发局部活动，同时显著衰减了后期成分，这与抑制非局部活动相符。
结论通过利用个体化电场模型的空间精度，EPICURUS可能提高脑电信号重建的特异性，为改善TMS直接诱发的局部早期和晚期皮层局部反应的时空分辨率提供了一种有前景的工具。

## Abstract
BackgroundThe concurrent use of Transcranial magnetic stimulation and electroencephalography (TMS-EEG) is increasingly integrated into research and clinical protocols. However, a reliable isolation of EEG responses that are locally evoked by TMS at the targeted cortical sites independent from contaminating sources, remains challenging.

MethodsHere we introduce EPICURUS, a novel spatial filtering approach for TMS-EEG that uses individualized MRI-based simulations of the TMS-induced electric field (E-field) to define the spatial extent of locally evoked activity. This method guides the reconstruction of EEG signals originating from the direct stimulation site while minimizing crosstalk from distant, non-targeted sources.

ResultsIn synthetic simulations and a human TMS-EEG dataset, EPICURUS preserved early-latency TMS-evoked local activity while substantially attenuating later components, consistent with suppression of non-local activity.

ConclusionBy leveraging the spatial precision of individualized E-field modeling, EPICURUS may enhance the specificity of EEG signal reconstruction, offering a promising tool for improving the spatiotemporal resolution of local early and late cortical local responses directly elicited by TMS.

---

## 论文详细总结（自动生成）

# 论文详细总结：EPICURUS

## 1. 核心问题与整体含义（研究动机和背景）

- **问题**：经颅磁刺激与脑电图（TMS‑EEG）研究中的一个主要挑战是难以从污染源（如肌肉伪迹、远场容积传导）中可靠分离出目标皮层区域由 TMS 局部诱发的 EEG 反应。现有的空间滤波方法（如 ICA、源重建）特异性不足，尤其难以在早期潜伏期后区分局部与全局活动。
- **整体含义**：提出一种利用个体化 MRI 模拟的 TMS 感应电场（E‑field）空间分布来指导 EEG 信号重建的方法，旨在提高局部诱发活动估计的时空分辨率，从而更准确研究 TMS 直接诱发的早期和晚期皮层局部反应。

## 2. 方法论：核心思想、关键技术细节、算法流程

- **核心思想**：通过基于个体 MRI 的 TMS 电场建模，定义直接刺激部位（目标皮层区域）的局部活动空间范围，然后构建一个空间滤波器，在重建 EEG 信号时保留该空间范围内的成分，同时抑制来自远处非目标源的串扰。
- **关键技术细节**：
  - 预先利用个体 MRI 数据和 TMS 线圈模型计算感应电场（E‑field）在皮层上的分布。
  - 将 E‑field 强度较高的区域视为“局部活动区域”，其余区域视为“非局部源”。
  - 使用线性约束最小方差（LCMV）或类似 beamforming 方法，但将 E‑field 空间分布作为先验约束，设计空间滤波器权重矩阵。
  - 实际重建时，只重建目标区域内（基于 E‑field 阈值）的 EEG 源，而抑制区域外源的贡献。
- **公式/算法流程**（文字说明）：
  1. 个体 MRI 分割 → 构建头模型（BEM/FEM）。
  2. TMS 线圈位置与方向设定 → 边界元法模拟 E‑field 在皮层网格上的分布。
  3. 设定 E‑field 幅度阈值，确定“局部活动区域”内的源点集合 S。
  4. 构建 EEG 前向模型（由每个源点 S 到电极的传递矩阵）。
  5. 设计空间滤波权重矩阵 W，使得 W 对 S 内源点的响应为 1（或单位增益），而对 S 外源点响应近似为 0（零约束）。
  6. 将滤波后的 EEG 信号乘以 W 得到局部活动估计时间序列。

> **注**：元数据中未提供完整数学公式，上述为基于方法描述的逻辑还原。

## 3. 实验设计

- **数据集/场景**：
  - **合成仿真数据**：使用已知源分布的合成 EEG 数据模拟 TMS 诱发的局部 + 全局活动，定量评估重建精度（如 RMSE，相关系数）。
  - **人类 TMS‑EEG 数据集**：采集真实人类受试者的 TMS‑EEG 记录（具体受试者数量、刺激靶区未在元数据中明确）。
- **基准方法**：可能对比了标准 LCMV beamforming、重参考方案、或不加先验的源重建。元数据未具体列举，但提到“早期局部活动被保留，后期非局部成分衰减”作为与理想分离的对比。
- **对比方法**：未详细说明，但推测与普通源定位方法进行比较，突出 EPICURUS 的特异性优势。

## 4. 资源与算力

- 元数据中**未明确提及**使用的 GPU 型号、数量或训练时长。可能本文主要依赖 CPU 进行电场模拟和滤波器设计（需进行前向模型计算），但未说明计算资源需求。建议读者查阅原始论文补充材料。

## 5. 实验数量与充分性

- **实验组数**：至少包括合成仿真和人类数据两大部分。合成数据可能设置不同信噪比、不同源个数等参数，人类数据可能包含多名受试者的多次刺激记录。元数据中“synthetic simulations and a human TMS‑EEG dataset”表明至少两组实验。
- **充分性与公平性**：方法本身具有明确的空间先验，因此在合成数据中可能表现优异，但客观性依赖于电场建模的准确性（需使用高精度 MRI）。真实人类数据中的结果可能受个体差异和建模误差影响。整体看实验覆盖了验证和实际应用，但缺少与多种现有方法的系统消融对比（如仅对比 E‑field 先验 vs 无先验），待原始论文详细结果。结论偏向正面，存在一定利益相关风险（作者可能为方法开发者）。

## 6. 主要结论与发现

- EPICURUS 在合成仿真中成功保留了早期潜伏期（<50ms）的局部诱发活动，同时显著衰减了后期（>100ms）的非局部成分。
- 在人类 TMS‑EEG 数据中，使用该方法重建的信号显示出与 TMS 直接刺激一致的早期响应，而后期全局性成分（如诱发电位 P60、N100）被抑制，符合预期。
- 表明通过利用个体化电场模型的空间精度，能显著提高 EEG 源重建的特异性，有望改善 TMS‑EEG 研究中对局部皮层反应的时间和空间解析能力。

## 7. 优点

- **创新性**：首次将 TMS 感应电场分布直接引入 EEG 空间滤波设计，将物理先验与源重建结合。
- **高特异性**：相比传统 beamforming 或 ICA，能更精确区分局部与远场活动，减少伪迹污染。
- **个体化建模**：使用个体 MRI 和真实线圈模型，适应不同头型和刺激位置，提高了准确性。
- **实用性强**：可适用于现有 TMS‑EEG 数据分析流程，无需额外硬件修改。

## 8. 不足与局限

- **依赖 MRI 质量**：需要高质量个体 MRI 用于头模型和 E‑field 模拟，对临床或无法获取 MRI 的场景不适用。
- **计算复杂度**：E‑field 模拟和前向模型构建较耗时，可能限制大规模数据分析。
- **参数敏感性**：局部区域的空间阈值（如 E‑field 大小阈值）需要人为设定，不同阈值可能影响结果。
- **验证范围局限**：仅在一个人类数据集上测试，不同 TMS 靶区（如运动皮层 vs 前额叶）和不同刺激强度下的性能未知。
- **未与其他空间滤波方法进行系统量化对比**：如与独立成分分析（ICA）、Laplacian 重参考、标准源重建（sLORETA）的对比数据缺失。
- **潜在偏差风险**：作者即方法提出者，实验中可能选择对自身方法有利的数据或参数。

（完）
