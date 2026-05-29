---
title: Variational autoencoder for interpretable seizure onset phases detection
title_zh: 用于可解释癫痫发作起始阶段检测的变分自编码器
authors: "Capallera, I., Mercadal, B., Bartolomei, F., Ruffini, G."
date: 2026-05-28
pdf: "https://www.biorxiv.org/content/10.1101/2025.09.09.675087v2.full.pdf"
tags: ["query:eeg-ode-ln"]
score: 9.0
evidence: 基于变分自编码器的SEEG发作起始检测
tldr: 癫痫手术评估需识别SEEG中的发作期和低电压快活动(LVFA)起始。本文提出首个基于一维变分自编码器(VAE)的深度学习框架，编码2秒SEEG片段至60维潜空间，经线性分类和后处理实现每通道0.5秒分辨率的ictal与LVFA标记。在37名患者中，片段级三类平均召回0.88；通道级ictal召回0.84（SOZ通道0.91），LVFA召回0.74，中位延迟分别5.0s和0.86s。潜维度与幅度、频带功率等生理特征可解释。该框架首次联合自动标注ictal和LVFA onset，提供了稳健可解释的SEEG分析平台，有望显著减少临床医生工作量。
source: biorxiv
selection_source: fresh_fetch
motivation: 现有方法缺乏同时、逐通道、时间分辨地自动标注SEEG中ictal和LVFA起始的能力，临床医生标注工作繁重。
method: 使用一维VAE编码2秒SEEG片段至60维潜空间，线性分类器分为发作间期、ictal和LVFA，后处理生成每通道0.5秒分辨率起始标记。
result: "片段级三类平均召回0.88；通道级ictal召回0.84（SOZ通道0.91），LVFA召回0.74；中位起始延迟分别为5.0s和0.86s；作为癫痫检测器召回99.1%且假阳性1%。"
conclusion: 首个联合ictal和LVFA的逐通道时间分辨框架，可解释性强，性能优异，有潜力自动化SEEG分析以减轻临床负担。
---

## 摘要
目的：我们提出了第一个深度学习框架，用于在局灶性癫痫患者的立体脑电图（SEEG）记录中自动、时间分辨、逐通道标注发作期和低电压快活动（LVFA）起始。据我们所知，之前没有系统能够在连续单通道记录上联合解决这些任务。方法：一维变分自编码器（VAE）将2秒的SEEG片段编码为60维潜在空间，并通过线性分类器将其分类为发作间期、发作期或LVFA。后处理算法将片段级概率转换为0.5秒分辨率的逐通道起始标记。该系统在37名具有手动发作期和LVFA标注的患者上，使用受试者级5折交叉验证进行训练和评估。主要结果：在片段级别，VAE对三个类别的平均召回率为0.88。在通道级别，发作期召回率达到0.84（在发作起始区通道上为0.91），LVFA召回率为0.74，中位起始潜伏期分别为5.0秒和0.86秒。作为癫痫检测器，该系统实现了99.1%的召回率，假阳性率为1%。潜在维度与生理可解释的特征（幅度、频带功率、频谱平坦度、能量比）相关。消融研究表明，VAE的重建目标相对于仅判别性编码器的基线具有双重优势：改进的检测性能以及潜在维度与这些临床有意义特征之间更强的对齐。意义：通过提供首个用于联合发作期和LVFA标注的时间分辨逐通道框架，这项工作为自动SEEG分析建立了一个稳健且可解释的平台，有可能在术前癫痫评估中显著减少临床医生的工作量。

## Abstract
Objective: We present the first deep learning framework for automated, time-resolved, per-channel annotation of ictal and Low-Voltage Fast Activity (LVFA) onsets in stereo electroencephalography (SEEG) recordings of patients with focal epilepsy. To our knowledge, no prior system jointly addresses these tasks on continuous single-channel recordings. Approach: A one-dimensional Variational Autoencoder (VAE) encodes 2-second SEEG segments into a 60-dimensional latent space and classifies them as interictal, ictal, or LVFA via a linear classifier. A postprocessing algorithm converts segment-level probabilities into per-channel onset markers at 0.5-second resolution. The system was trained and evaluated using subject-wise 5-fold cross-validation on 37 patients with manual ictal and LVFA annotations.Main results: At the segment level, the VAE classified the three classes with an average recall of 0.88. At the channel level, it reached an ictal recall of 0.84 (0.91 on Seizure Onset Zone channels) and LVFA recall of 0.74, with median onset latencies of 5.0s and 0.86s, respectively. As a seizure detector, the system achieved 99.1% recall with 1% false positives. Latent dimensions correlated with physiologically interpretable features (amplitude, band powers, spectral flatness, energy ratio). An ablation study showed that the VAE's reconstruction objective provides dual benefits over a discriminative encoder-only baseline: improved detection performance and stronger alignment between latent dimensions and these clinically meaningful features. Significance: By providing the first time-resolved per-channel framework for joint ictal and LVFA annotation, this work establishes a robust and explainable platform for automated SEEG analysis with potential to substantially reduce clinician workload during presurgical epilepsy evaluation.

---

## 论文详细总结（自动生成）

### 1. 论文的核心问题与整体含义（研究动机和背景）
癫痫手术评估中，临床医生需要从立体脑电图（SEEG）中手动标注发作期（ictal）和低电压快活动（LVFA）的起始时间，这一过程耗时且主观性强。现有自动化方法要么只检测发作期，要么无法实现逐通道、时间分辨的联合标注。本文旨在提出首个深度学习框架，能够同时、自动地在连续单通道SEEG记录中标记ictal和LVFA起始，以减轻临床负担，提高术前评估效率和一致性。

### 2. 论文提出的方法论：核心思想、关键技术细节
- **核心思想**：使用一维变分自编码器（VAE）将2秒的SEEG片段编码为60维潜在空间，通过在潜空间上训练线性分类器来区分发作间期、ictal和LVFA三类，再通过后处理将片段级概率转换为每通道0.5秒分辨率的起始标记。该方法同时利用VAE的重建目标来增强潜在表示的可解释性。
- **关键技术细节**：
  - 输入：2秒SEEG单通道片段。
  - VAE编码器输出60维潜变量（均值和对数方差），解码器重建输入。
  - 在60维潜空间上训练线性分类器（逻辑回归或线性SVM，文中未明确但推测为线性分类器）。
  - 后处理算法：将片段级分类概率通过阈值和时序平滑转换为每通道的ictal和LVFA起始时间点（0.5秒分辨率）。
  - 训练与评估：使用受试者级5折交叉验证，在37名有手动标注的患者数据上训练和测试。

### 3. 实验设计：数据集、基准、对比方法
- **数据集**：37名局灶性癫痫患者的SEEG记录，包含手动标注的ictal和LVFA起始时间（发作起始区SOZ通道标注）。未见公开数据集名称，可能是医院内部数据。
- **基准**：未明确列出外部基准方法。内部对比为消融实验：将VAE（有重建目标）与仅判别性编码器（无重建目标）基线进行比较。
- **对比方法**：主要对比的是有无VAE重建目标的差异，以及不同分类器或特征提取方式（未具体列举其他深度学习模型）。

### 4. 资源与算力
论文摘要及元数据中**未明确说明**使用的GPU型号、数量或训练时长。仅提到使用VAE编码器（可能为简单CNN或MLP），计算量不大，但具体资源需求未知。

### 5. 实验数量与充分性
- **实验数量**：
  - 主实验：5折交叉验证，在37名患者上评估片段级和通道级性能。
  - 消融实验：对比VAE与仅判别性编码器。
  - 其他分析：潜在维度与生理特征（幅度、频带功率、频谱平坦度、能量比）的相关性分析。
- **充分性评价**：实验设计较为充分，包括了片段级、通道级、检测器性能多个层面。但缺乏与其他现有方法的直接对比（如传统特征+分类器、其他深度学习模型），消融实验仅对比了一个基线，公平性尚可但不够全面。此外，数据集规模（37名患者）较小，可能影响泛化性。

### 6. 论文的主要结论与发现
- 片段级三类（发作间期、ictal、LVFA）平均召回率0.88。
- 通道级ictal召回率0.84（SOZ通道召回率0.91），LVFA召回率0.74。
- 中位起始潜伏期：ictal 5.0秒，LVFA 0.86秒。
- 作为癫痫检测器（二分类：发作vs.非发作），召回率99.1%，假阳性率1%。
- 隐空间维度与幅度、频带功率等生理特征显著相关，说明VAE提供了可解释表示。
- 消融实验证明VAE重建目标同时提升了检测性能和潜空间可解释性。

### 7. 优点
- **首个联合ictal和LVFA的逐通道时间分辨框架**，填补了自动化SEEG分析空白。
- **可解释性强**：潜空间特征与生理指标相关，有利于临床信任。
- **性能优异**：检测器召回率99.1%且低假阳性，ictal/LVFA延迟较低。
- **方法相对简洁**：VAE+线性分类器，易于部署和推广。
- **交叉验证策略**：按受试者划分，避免数据泄露。

### 8. 不足与局限
- **数据集规模有限**：仅37名患者，可能未覆盖多种癫痫类型或电极位置，泛化性存疑。
- **缺乏与外部方法和公开基准的直接比较**：难以评估在当前领域的相对领先程度。
- **算力需求未报告**：无法判断资源消耗是否合理。
- **后处理参数依赖手动阈值**：可能在不同中心需调整。
- **对LVFA的召回率（0.74）低于ictal**，在低信噪比或短时LVFA上可能漏检。
- **延迟指标**：ictal中位延迟5秒相对较长，可能对临床实时干预意义有限（但标注任务可接受）。
- **标注一致性**：手动标注本身存在主观性，未报告标注者间一致性。

（完）
