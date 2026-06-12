---
title: "Source-space EEG functional connectivity and prediction of cognition in Parkinsons disease: No added benefit of individualized head models over standard templates"
title_zh: 源空间脑电图功能连接与帕金森病认知预测：个性化头部模型相对于标准模板无额外优势
authors: "Tetereva, A., Hall-McMaster, G., Slater, N., Harris, A., Shoorangiz, R., Le Heron, C., Keenan, R., Myall, D., Pitcher, T., Kirk, I., Meissner, W., Anderson, T., Melzer, T., Pat, N., Dalrymple-Alford, J."
date: 2026-06-11
pdf: "https://www.biorxiv.org/content/10.64898/2026.05.07.723671v2.full.pdf"
tags: ["query:eeg-ode-ln"]
score: 7.0
evidence: 基于源空间功能连接的EEG信号解码
tldr: 针对帕金森病认知衰退缺乏可靠生物标志物的问题，本研究比较了个体化MRI头模型与标准模板头模型在源空间脑电功能连接预测认知表现上的效果。通过分析136名患者和51名对照的静息态脑电数据，使用HCP-MMP1图谱及六种频带的AEC和dwPLI指标，结合六种机器学习算法进行预测。结果发现θ、α、β频带功能连接预测效果最佳，两种头模型预测性能几乎一致。研究表明标准模板头模型足以作为临床实用的脑电功能连接生物标志物，便于推广。
source: biorxiv
selection_source: fresh_fetch
motivation: 认知下降是帕金森病重要非运动症状，但缺乏可靠、易获取的生物标志物，且源空间脑电功能连接建模是否必须个体化MRI未知。
method: 比较个体化MRI与标准模板两种头模型，基于HCP-MMP1图谱提取六频段AEC和dwPLI功能连接，使用六种回归算法嵌套交叉验证预测认知。
result: θ、α、β频段功能连接预测最佳，最大R²=0.170，最大r=0.439；两种头模型预测性能及神经解剖特征重要性模式相似。
conclusion: 源空间静息态脑电功能连接可预测帕金森病认知表现，标准模板头模型足够有效，支持临床可及的EEG生物标志物应用。
---

## 摘要
引言：认知衰退是帕金森病（PD）的主要非运动特征，但目前可靠且易获取的生物标志物仍然有限。静息态脑电图（EEG）因其低成本、便携且适合重复评估而成为有潜力的候选标志物。近年来越来越多的研究关注于源空间功能连接（FC）来预测认知能力。然而，基于个体化MRI头部模型与基于标准模板模型的源建模对预测效果的影响尚不明确。方法：为比较这两种源空间EEG FC方法，我们分析了新西兰帕金森病进展项目中的EEG数据，包括136名PD患者和51名年龄匹配的对照者。基于HCP-MMP1图谱分割的源空间静息态EEG，用于提取六个典型频段的振幅包络相关（AEC）和去偏加权相位滞后指数（dwPLI）。在嵌套交叉验证框架内，使用六种机器学习回归算法评估得到的二十四种FC模态。结果：θ、α和β频段的FC对整体认知的预测最为一致。θ和α频段的AEC和dwPLI特征表现最佳（最大R² = 0.170，95% CI = 0.067-0.262；最大r = 0.439，95% CI = 0.328-0.537）。标准头部模型和个体化头部模型在几乎所有模态上的预测性能相当。两种头部模型选项的Cole-Anticevic网络特征重要性神经解剖模式也相似。结论：我们发现源空间静息态EEG FC可以预测PD的认知表现。两种头部模型的可比性表明，更用户友好且资源消耗更少的标准模板头部模型足以完成这一任务。这支持了基于EEG的FC作为PD认知生物标志物的可行性、可扩展性和临床可及性。

## Abstract
Introduction: Cognitive decline is a major non-motor feature of Parkinson s disease (PD), but reliable and accessible biomarkers remain limited. Resting-state electroencephalography (EEG) is a promising candidate because it is low-cost, portable, and well suited to repeated assessment. Recent work has increasingly focused on source-space functional connectivity (FC) for the prediction of cognition. However, the influence of source modelling based on an individualized MRI-based head model relative to that based on standard template model is unknown. Methods: To compare these two source-space EEG FC methods, we analysed EEG data from the New Zealand Parkinson s Progression Programme, including 136 people with PD and 51 age-similar controls. Source space resting-state EEG, parcellated with the HCP-MMP1 atlas, was used to derive amplitude envelope correlation (AEC) and debiased weighted phase lag index (dwPLI) across six canonical frequency bands. The resulting twenty-four FC modalities were evaluated using six machine-learning regression algorithms within a nested cross-validation framework. Results: Theta-, alpha-, and beta-band FC showed the most consistent prediction of global cognition. The strongest performance was observed for theta- and alpha-band AEC and dwPLI features (max R2 = 0.170, 95% CI = 0.067-0.262; max r = 0.439, 95% CI = 0.328-0.537). Standard and individualized head models showed comparable predictive performance across nearly all modalities. The feature-importance neuroanatomical patterns for Cole-Anticevic networks were also similar between the two head-model options. Conclusions: We found that source-space resting-state EEG FC can predict cognitive performance in PD. The comparability of the two head models suggests that the more user-friendly and less resource-intensive standard template head model is sufficient for this purpose. This supports feasible, scalable, and clinically accessible EEG-based FC biomarkers of cognition in PD.