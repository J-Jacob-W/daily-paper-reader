---
title: Noninvasive and Objective Near Real-Time Detection of Pain Changes During Tonic Fluctuating Noxious Heat Stimulation
title_zh: 在紧张波动性伤害性热刺激期间无创且客观的近实时疼痛变化检测
authors: "Visser, L., Buechel, C."
date: 2026-06-20
pdf: "https://www.biorxiv.org/content/10.64898/2026.01.26.701710v4.full.pdf"
tags: ["query:eeg-ode-ln"]
score: 7.0
evidence: 使用8通道EEG信号解码疼痛变化
tldr: 慢性疼痛的自然波动使患者难以控制，客观检测疼痛减轻有助于闭环干预。本研究采集多模态生理信号（EDA、心率、瞳孔等），使用最小预处理的Transformer模型分类疼痛减轻。最佳组合AUROC达0.854，中位检测延迟5.75秒。结果表明EDA等信号可简单部署，为精准干预奠定基础。
source: biorxiv
selection_source: fresh_fetch
motivation: 慢性疼痛患者无法控制疼痛波动，客观检测疼痛减轻可增强控制感并指导干预时机。
method: 采集42名受试者在波动热刺激下的多模态生理信号，使用最小预处理的Transformer模型分类疼痛减轻与非减轻。
result: 结合EDA、心率和瞳孔直径的Transformer模型AUROC=0.854，中位延迟5.75秒，EDA为最优单信号。
conclusion: EDA和心率可有效检测疼痛变化，为实际闭环系统提供可行方案，而EEG等需个性化微调。
---

## 摘要
慢性疼痛涉及患者无法控制的自然强度波动，导致习得性无助和功能受损。检测自发性疼痛减轻可实现精准定时干预，增强患者的控制感。然而，现有的客观疼痛评估研究主要集中于从短暂、可预测的刺激中估计静态强度，而非检测持续疼痛的实时变化。本研究探讨了在波动性疼痛期间，是否可以利用易于获取的生理信号客观检测疼痛减轻。我们记录了42名健康参与者（平均年龄26.2岁，标准差5.1）在左前臂进行校准的紧张性伤害性热刺激（视觉模拟量表0-70分；十二次3分钟试验）过程中的多种生理信号（8通道脑电图、皮肤电活动、心率、瞳孔直径、面部表情）。温度变化持续5-20秒。采用适合实时应用的最小预处理，我们训练深度学习模型，根据短暂时间窗口对疼痛减轻与非减轻进行分类，并在保留的测试集（9名参与者）上进行评估。结合皮肤电活动、心率与瞳孔直径，使用基于变换器的架构获得了最优分类性能（AUROC=0.854，准确率=76.8%）。皮肤电活动成为信息量最大的单一预测指标。连续流分析显示中位检测延迟为5.75秒，灵敏度为70.4%，可将延迟降低至4.25秒，但以增加假阳性为代价。结果表明，皮肤电活动与心率便于直接实际部署，而脑电图和面部表情等高度变异的信号则需要个性化微调模型。这些发现为针对自发性疼痛变化的闭环干预奠定了基础。

## Abstract
Chronic pain involves natural intensity fluctuations that patients cannot control, contributing to learned helplessness and functional impairment. Detecting spontaneous pain decreases could enable precisely timed interventions that enhance perceived control. However, existing research on objective pain assessment has focused primarily on estimating static intensity from short, predictable stimuli rather than detecting moment-to-moment changes in ongoing pain. This study investigated whether pain decreases can be detected objectively using easily obtainable physiological signals during fluctuating pain. We recorded multiple physiological signals (8-channel EEG, electrodermal activity, heart rate, pupil diameter, facial expressions) from 42 healthy participants (M_age = 26.2 years, SD = 5.1) during calibrated tonic noxious heat stimulation on the left forearm with unpredictable intensity fluctuations (0-70 on visual analogue scale; twelve 3-minute trials). Temperature changes lasted 5-20 seconds. Using minimal preprocessing suitable for real-time applications, we trained deep learning models to classify pain decreases versus non-decreases from brief temporal windows, evaluated on a held-out test set (9 participants). Combining electrodermal activity, heart rate, and pupil diameter yielded optimal classification performance using a transformer-based architecture (AUROC = 0.854, accuracy = 76.8%). Electrodermal activity emerged as the most informative single predictor. Continuous stream analysis demonstrated median detection latency of 5.75 seconds with 70.4% sensitivity, reducible to 4.25 seconds at the cost of increased false positives. Results indicate that electrodermal activity and heart rate enable straightforward practical deployment, while highly variable signals such as EEG and facial expressions require personalized fine-tuned models. These findings establish a basis for closed-loop interventions targeting spontaneous pain changes.