---
title: "DLC2Action: A Multimodal Deep Learning-based Toolbox for Automated Behavior Segmentation"
title_zh: DLC2Action：基于多模态深度学习的自动化行为分割工具箱
authors: "Kozlova, E., Bonnetto, A., Mathis, A."
date: 2026-05-30
pdf: "https://www.biorxiv.org/content/10.1101/2025.09.27.678941v2.full.pdf"
tags: ["query:multi-modal"]
score: 7.0
evidence: 基于视频、音频和姿态的多模态深度学习行为分割工具箱
tldr: 行为分析是神经科学的基础，但人工标注行为成为瓶颈。DLC2Action工具箱集成多种深度学习架构，支持从视频、音频和姿态数据自动分割行为。通过自监督学习缓解标注稀缺问题，在9个数据集上达到强性能。还发现Atari游戏中眼球运动可预测按键。其图形界面简化了标注流程，模块化设计便于扩展。
source: biorxiv
selection_source: fresh_fetch
motivation: 手动标注行为数据耗时且可重复性差，需要自动化工具。
method: 集成多种SOTA深度学习架构进行行为分割，支持自监督学习与多模态数据。
result: 在9个数据集上达到强性能，Atari游戏中眼球运动预测按键。
conclusion: DLC2Action提供高效、可扩展的自动行为分割方案。
---

## 摘要
行为分析是神经科学的基础，然而手动标注行为动作仍然是制约实验规模和可重复性的瓶颈。本文介绍DLC2Action，一个开源的Python工具箱，能够从视频、音频以及估计的2D/3D姿态追踪数据中自动进行行为标注。DLC2Action集成了多个针对动作分割优化的最先进深度学习架构，并支持自监督学习（SSL）以解决标注稀缺问题，在有限标注数据集上提升性能。为便于模型比较，我们为九个不同数据集（包括啮齿动物实验、人类烹饪研究和野生动物观察）建立了固定的训练/测试划分。DLC2Action在这些基准测试中取得了强劲的性能。为进一步展示该工具的通用性，我们将其应用于Atari游戏数据，发现在某些游戏中，玩家的眼球运动能够跨被试一致地预测其按键操作。由于DLC2Action具有直观的图形用户界面（GUI），用户可以简化行为标注、执行主动学习以及评估模型预测。支持多种姿态、视频和标注格式。最后，DLC2Action采用模块化设计，易于扩展，允许用户集成新模型、数据集特征和方法。代码和基准测试可访问：https://github.com/amathislab/DLC2action

## Abstract
Behavioral analysis is fundamental to neuroscience, yet the manual annotation of actions remains a bottleneck that constrains both the scale and the reproducibility of experiment. Here, we present DLC2Action, an open-source Python toolbox that enables automatic behavior annotation from video, audio and estimated 2D/3D pose tracking data. DLC2Action integrates multiple state-of-the-art deep learning architectures optimized for action segmentation and supports self-supervised learning (SSL) to address annotation scarcity, boosting performance with limited labeled datasets. To enable model comparison, we establish fixed train/test partitions for nine diverse datasets comprising rodent experiments, human cooking studies, and wildlife observation. DLC2Action reached strong performance across those benchmarks. To further showcase the tool's versatility, we applied it to Atari gameplay data and found that, in certain games, the players' eye movements consistently predict their button presses across subjects. Because DLC2Action features an intuitive graphical user interface (GUI), users can streamline behavior annotation, perform active learning, and assess of model predictions. Diverse pose, video, and annotation formats are supported. Lastly, DLC2Action is modular and thus designed for extensibility, allowing users to integrate new models, dataset features, and methods. The code and benchmarks are available at: https://github.com/amathislab/DLC2action