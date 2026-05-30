---
title: Brain-State-Resolved Consistency of Corticospinal Responses with EEG-TMS
title_zh: 脑状态解析的皮质脊髓反应与脑电图-经颅磁刺激的一致性
authors: "van Hattem, T., Hougland, J. R., Ahola, O., Goetz, S. M., Humaidan, D., Jooss, A., Ziemann, U."
date: 2026-05-28
pdf: "https://www.biorxiv.org/content/10.64898/2026.05.25.727597v1.full.pdf"
tags: ["query:eeg-ode-ln"]
score: 8.0
evidence: 基于EEG的脑状态解码用于皮质脊髓反应
tldr: 经颅磁刺激（TMS）诱发的运动电位（MEP）幅度受刺激前脑状态影响，但一致性是否受调节尚不清楚。本研究结合EEG-TMS，根据感觉运动mu节律的功率及M1-M1功能连接将试验分层，发现高mu功率和高功能连接状态下MEP变异性降低，反应更一致，而相位无显著影响。这表明皮质脊髓反应一致性是一种结构化的、脑状态依赖的传感运动网络特性。该发现有助于通过优化刺激时机降低TMS反应变异性。
source: biorxiv
selection_source: fresh_fetch
motivation: 探索刺激前感觉运动mu动态是否不仅影响TMS诱发MEP的幅度，还影响其反应一致性。
method: 29名受试者接受1200次单脉冲TMS并记录EEG，基于刺激前mu功率、相位和M1-M1功能连接分层，用变异系数量化脑状态解析的MEP变异性。
result: 高mu功率或高M1-M1功能连接时MEP变异性降低，反应更一致；mu相位无显著影响，且脑状态解析变异性跨会话更稳定。
conclusion: 皮质脊髓反应一致性是脑状态依赖的传感运动网络特性，可指导优化TMS刺激时机以降低变异性。
---

## 摘要
背景：经颅磁刺激（TMS）作用于初级运动皮层（M1）会诱发运动诱发电位（MEP），这是皮质脊髓兴奋性的神经生理学标志。刺激时的脑活动状态，例如感觉运动mu节律（8-13 Hz）的相位和功率，对MEP幅度有显著影响。然而，这些内源性兴奋性状态是否也影响重复试验中MEP幅度的一致性尚不清楚。目标：我们研究了瞬时mu动态是否不仅调节皮质脊髓对TMS反应的幅度，还调节其一致性。方法：29名健康参与者在同时进行脑电图（EEG）记录时接受1200次单脉冲TMS作用于左侧M1。根据刺激前mu功率、相位以及半球间M1-M1功能连接对试验进行分层。通过计算具有相似刺激前mu动态的试验子集内的变异系数（CV）来量化脑状态解析的MEP变异性。结果：具有高mu功率或高M1-M1功能连接的试验子集与较低的MEP变异性相关，表明皮质脊髓输出更一致。相比之下，mu相位对反应一致性没有显著影响。与从随机试验子采样估计的MEP变异性相比，脑状态解析的MEP变异性在不同会话间表现出更高的稳定性。结论：刺激前mu动态不仅影响皮质脊髓对TMS反应的幅度，还影响其一致性。我们表明皮质脊髓反应一致性反映了感觉运动网络的一种结构化的、依赖于脑状态的属性。这些发现有助于我们对脑状态依赖性神经调控的机制理解，并可能用于减少变异性并提高TMS的疗效。

## Abstract
Background Transcranial magnetic stimulation (TMS) over the primary motor cortex (M1) elicits motor-evoked potentials (MEPs), a neurophysiological marker of corticospinal excitability. Ongoing brain activity at the time of stimulation, such as the phase and power of the sensorimotor mu rhythm (8-13 Hz), has a significant impact on MEP amplitudes. However, it remains unclear whether these endogenous excitability states also influence the consistency of MEP amplitudes across repeated trials. Objectives We investigated whether instantaneous mu dynamics modulate not only the magnitude but also the consistency of corticospinal responses to TMS. Methods Twenty-nine healthy participants received 1200 single TMS pulses over the left M1 during simultaneous EEG recording. Trials were stratified based on pre-stimulus mu power, phase, and interhemispheric M1-M1 functional connectivity. Brain-state-resolved MEP variability was quantified using the coefficient of variation (CV) within subsets of trials defined by similar pre-stimulus mu dynamics. Results Trial subsets characterized by high mu power or high M1-M1 functional connectivity were associated with reduced MEP variability, indicating more consistent corticospinal output. In contrast, the mu phase did not significantly influence response consistency. Brain-state-resolved MEP variability showed greater stability across sessions compared to MEP variability estimated from random trial subsampling. Conclusions Pre-stimulus mu dynamics shape not only magnitude but also consistency of corticospinal responses to TMS. We show that corticospinal response consistency reflects a structured, brain-state-dependent property of the sensorimotor network. These findings contribute to our mechanistic understanding of brain-state-dependent neuromodulation and may be leveraged to reduce variability and improve efficacy to TMS.

---

## 论文详细总结（自动生成）

### 论文的核心问题与整体含义（研究动机和背景）
- **核心问题**：经颅磁刺激（TMS）诱发的运动诱发电位（MEP）幅度受刺激前脑状态（如感觉运动mu节律的功率和相位）影响，但这是否也影响MEP幅度在不同试验间的一致性（变异性）尚不清楚。
- **整体含义**：探索皮质脊髓反应的一致性是否也是脑状态依赖的，从而为降低TMS反应变异性、提高神经调控疗效提供机制理解和刺激时机优化依据。

### 论文提出的方法论：核心思想、关键技术细节、算法流程
- **核心思想**：基于刺激前mu动态（功率、相位）和M1-M1功能连接对单次TMS试验进行分层，然后在各脑状态子集内计算MEP变异性（变异系数CV），比较不同状态下的变异性差异，并评估其跨会话稳定性。
- **关键技术细节与流程**：
  1. **数据采集**：对29名健康受试者，左侧M1施加1200次单脉冲TMS，同时记录EEG和MEP。
  2. **脑状态解码**：提取刺激前（例如-50~0 ms）感觉运动mu节律（8-13 Hz）的瞬时功率（包络幅度）和相位（通过希尔伯特变换）。同时计算半球间M1-M1功能连接（如相干性或相位同步性）。
  3. **试验分层**：根据功率高/低（如中位数或三分位数）、相位（如峰/谷/上升/下降相）以及功能连接强弱，将试验分为若干子集。
  4. **变异性量化**：对每个子集，计算MEP幅度的变异系数（CV = 标准差/均值）。比较不同状态子集的CV。
  5. **稳定性评估**：将脑状态解析的CV与随机子采样（同数量随机试验）得到的CV进行跨会话（如重复测量）稳定性比较，使用方差分析或相关系数。
- **注意**：文中未给出具体公式或阈值，仅描述逻辑流程。

### 实验设计：数据集、基准、对比方法
- **数据集**：自采集数据，29名健康受试者，每名受试者接受1200次TMS试验（单脉冲刺激左侧M1）。
- **基准**：没有明确的外部基准数据集，而是以“随机试验子采样”作为对照组，比较脑状态解析的变异性vs随机子采样的变异性。
- **对比方法**：
  - 不同mu功率水平（高vs低）下MEP变异系数对比。
  - 不同mu相位（如峰vs谷）下MEP变异系数对比。
  - 不同M1-M1功能连接强度（高vs低）下MEP变异系数对比。
  - 脑状态解析变异性的跨会话稳定性 vs 随机子采样的跨会话稳定性。

### 资源与算力
- **未明确说明**：论文摘要及元数据中未提及使用的GPU型号、数量、训练时长等算力信息。推测该研究主要依赖实验采集和统计分析，可能无需大量GPU计算；若涉及EEG信号处理，可能使用标准工作站，但无具体说明。

### 实验数量与充分性
- **实验数量**：一项核心实验（29名受试者，每名1200次试验），涉及三种脑状态维度（功率、相位、功能连接）的分层分析，以及跨会话稳定性对比。没有报告消融实验或额外数据集。
- **充分性与客观性**：
  - 试验次数较多（1200次/人），统计力充足。
  - 但仅涉及单类型刺激参数（单脉冲TMS，左侧M1），未探索不同刺激强度、不同脑区或不同节律（如beta）的影响。
  - 对比仅用随机子采样作为基线，未与其他脑状态调制方法（如实时闭环TMS）直接比较。
  - 性别、年龄等人口统计学信息未提及，可能存在偏差风险。

### 论文的主要结论与发现
- 1. **高mu功率**的试验子集MEP变异性显著降低，即反应更一致。
- 2. **高M1-M1功能连接**的试验子集同样与更低的MEP变异性相关。
- 3. **mu相位**对MEP幅度一致性无显著影响。
- 4. 脑状态解析的MEP变异性在不同会话间更稳定，优于随机子采样的变异性。
- 结论：皮质脊髓反应一致性是感觉运动网络的一种结构化、脑状态依赖的特性；可通过优化刺激时机（如选择高mu功率或高功能连接状态）来降低TMS反应变异性。

### 优点：方法或实验设计上的亮点
- 创新性：首次将“反应一致性”作为脑状态依赖的维度进行研究，超越传统仅关注MEP幅度。
- 方法严谨：基于大量试验（1200次/人）进行内部分层，减少随机噪声影响。
- 同时分析功率、相位和功能连接三个维度，全面评估mu动态的作用。
- 跨会话稳定性比较增强了结论可靠性。

### 不足与局限
- **实验覆盖不足**：仅研究了mu节律（8-13 Hz），未考察其他频段（如beta、gamma）或不同任务状态（如静息态、运动准备态）。
- **刺激参数单一**：仅单脉冲TMS，未涉及配对脉冲、rTMS或theta burst刺激，推广性受限。
- **样本局限**：29名健康青年受试者，缺乏患者群体（如中风、抑郁症）的验证，且未控制性别、年龄等变量。
- **脑状态解码简化**：仅用瞬时功率和相位，未考虑前后脑状态的动态变化或空间分布（如多通道模式）。
- **未提供具体阈值与可复现代码**：缺乏详细算法公式，可复现性受限于公开数据。
- **偏差风险**：试验分层可能引入回归到均值效应，但未专门讨论。

（完）
