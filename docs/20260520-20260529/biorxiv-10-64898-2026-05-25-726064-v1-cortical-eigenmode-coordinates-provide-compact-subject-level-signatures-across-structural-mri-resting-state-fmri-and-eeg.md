---
title: "Cortical eigenmode coordinates provide compact subject-level signatures across structural MRI, resting-state fMRI, and EEG"
title_zh: 皮质特征模坐标在结构MRI、静息态fMRI和EEG中提供紧凑的个体级特征表示
authors: "Park, H. G., Tarpey, T."
date: 2026-05-28
pdf: "https://www.biorxiv.org/content/10.64898/2026.05.25.726064v1.full.pdf"
tags: ["query:eeg-ode-ln"]
score: 6.0
evidence: 皮层特征模坐标作为结构MRI、功能MRI和EEG的共享表示
tldr: 多模态脑成像数据（sMRI、rs-fMRI、EEG）通常在不同空间分析，导致被试水平特征难以统一和解释。本研究提出利用皮层Laplace-Beltrami特征模态坐标作为几何对齐的公共语言，将各模态数据映射到同一坐标系。在MPI-LEMON数据集上，这种表示生成的紧凑被试特征在年龄预测任务中显著优于传统图谱/传感器PCA方法；多模态特征模态坐标PCA在中等维度达到高精度，而GEMF进一步提取低维共享成分，同时保持可解释性。结果表明该坐标系可作为构建多模态对齐、紧凑且可解释的被试脑特征的基础。
source: biorxiv
selection_source: fresh_fetch
motivation: 现有神经影像分析多在模态特定空间或基于图谱/传感器的摘要上进行，难以构建通用的可解释被试特征。
method: 将sMRI、rs-fMRI和EEG数据投影到皮层Laplace-Beltrami特征模态坐标，并采用多模态PCA和GEMF进行分解。
result: 特征模态坐标表示在年龄预测上性能优异；多模态PCA在中等维度优于传统低维方法；GEMF提供更低维共享表示。
conclusion: 皮层特征模态坐标可作为多模态对齐、紧凑且可解释的被试水平脑特征的基础。
---

## 摘要
多模态神经影像学的一个实际障碍是，结构MRI、fMRI和EEG通常在模态特定的空间中进行分析，或者简化为基于图谱和传感器的摘要，从而限制了构建共同、可解释的个体级脑特征。我们评估了皮质Laplace-Beltrami特征模坐标作为结构MRI（sMRI）、静息态fMRI（rs-fMRI）和EEG的共享几何对齐语言。在该框架中，sMRI形态测量场由皮质特征模系数表示，rs-fMRI由特征模时间序列系数的协方差表示，EEG由模式-频率-条件摘要表示。使用马克斯·普朗克研究所莱比锡心-脑-身体数据集（MPI-LEMON），我们比较了单模态特征模坐标摘要、多模态皮质特征模坐标PCA、传统图谱/传感器PCA和脊表示，以及几何特征模多视角分解（GEMF）。GEMF是一种结构化分解，在保持数据对象模态原生组织的同时，分离出共享变异和模态特定变异。特征模坐标表示产生了紧凑的个体级特征，对实足年龄和次要认知结果具有较强的外部效度。多模态皮质特征模坐标PCA是表现最佳的方法之一，在中等维度下达到了较高的年龄预测性能，并且始终优于传统的低维PCA。GEMF选择了更低维度的共享表示，并保持竞争力，同时受益于提供可解释的共享和模态特定因子。这些发现支持皮质特征模坐标作为紧凑、可解释且多模态对齐的个体级脑特征的实用基础。

## Abstract
A practical barrier in multimodal neuroimaging is that structural MRI, fMRI, and EEG are often analyzed in modality-specific spaces or reduced to atlas- and sensor-based summaries, limiting the construction of common, interpretable subject-level brain signatures. We evaluate cortical Laplace-Beltrami eigenmode coordinates as a shared geometry-aligned language for structural MRI (sMRI), resting-state fMRI (rs-fMRI), and EEG. In this framework, sMRI morphometric fields are represented by cortical eigenmode coefficients, rs-fMRI by covariance among eigenmode time-series coefficients, and EEG by mode-frequency-condition summaries. Using the Max Planck Institute Leipzig Mind-Brain-Body dataset (MPI-LEMON), we compared unimodal eigenmode-coordinate summaries, multimodal cortical eigenmode-coordinate PCA, conventional atlas/sensor-based PCA and ridge representations, and geometric eigenmode multiview factorization (GEMF). GEMF is a structured decomposition that preserves the modality-native organization of the data objects while separating shared from modality-specific variation. Eigenmode-coordinate representations yielded compact subject-level signatures with strong external validity for chronological age and a secondary cognitive outcome. Multimodal eigenmode-coordinate PCA was among the strongest-performing approaches, reached high age-prediction performance at moderate dimension, and consistently outperformed conventional low-dimensional PCA. GEMF selected an even lower-dimensional shared representation and remained competitive with the benefit of providing interpretable shared and modality-specific factors. These findings support cortical eigenmode coordinates as a practical foundation for compact, interpretable, and multimodally aligned subject-level brain signatures.