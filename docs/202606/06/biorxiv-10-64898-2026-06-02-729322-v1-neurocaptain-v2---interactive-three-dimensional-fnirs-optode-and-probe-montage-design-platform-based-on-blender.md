---
title: NeuroCaptain v2 - Interactive Three-Dimensional fNIRS Optode and Probe Montage Design Platform Based on Blender
title_zh: NeuroCaptain v2 - 基于Blender的交互式三维fNIRS光纤和探头布局设计平台
authors: "McCann, A., Fang, Q."
date: 2026-06-05
pdf: "https://www.biorxiv.org/content/10.64898/2026.06.02.729322v1.full.pdf"
tags: ["query:eeg-ode-ln"]
score: 8.0
evidence: 功能性近红外光谱光极布局设计平台
tldr: "传统fNIRS探头布局设计依赖2D到3D转换，导致跨被试放置变异大。NeuroCaptain v2基于Blender，允许在3D头表面直接交互式放置和编辑光极，利用物理模拟松弛布局和蒙特卡罗计算灵敏度。跨7个脑图谱配准的平均光极位置标准差仅2.29 mm，比传统方法降低74%。该工具提供了可重复、开源的工作流，支持解剖引导的三维探头设计。"
source: biorxiv
selection_source: fresh_fetch
motivation: 传统二维到三维探头布局转换引入跨被试变异，需提高复现性。
method: 在Blender三维头表面交互设计光极，用物理引擎松弛布局，基于10-20网格存储重心坐标。
result: "跨7个发育脑图谱配准，平均每光极标准差2.29 mm，变异降低74%。"
conclusion: NeuroCaptain v2实现可重复、开源的三维fNIRS探头设计，支持解剖引导和跨被试注册。
---

## 摘要
意义：准确且可重复的光纤放置对于在个体和群体水平的神经影像学研究中获取高质量的fNIRS数据至关重要。传统的光纤/探头布局设计工具通常使用质量-弹簧模型将二维笛卡尔空间中定义的探头布局转换到三维头部表面。这种机械变换，加上二维探头定义与三维目标空间之间的间接映射，可能导致不同头部表面和受试者之间的放置变异。目的：我们介绍NeuroCaptain v2，这是一个基于Blender的开源插件，旨在实现交互式、解剖引导的光纤设计、配准以及fNIRS头帽和探头创建的皮层灵敏度可视化。方法：NeuroCaptain v2使研究人员能够直接在三维头部表面网格上添加、移动和编辑fNIRS光源和探测器，定义锚定光纤位置，并设置相邻光纤之间弹簧的刚度。然后利用Blender内置的物理模拟引擎松弛初始探头布局以满足机械约束。借助内置的基于网格的蒙特卡洛（MMC）和扩散求解器Redbird，NeuroCaptain v2计算并渲染三维灵敏度图，以指导迭代光纤调整。生成的三维光纤布局以在10-20标志网格中定义的重心坐标形式存储，可实现跨不同头部模型的一致探头转移。结果：我们展示了跨多个头部几何形状的交互式三维布局设计、跨头颅图谱探头配准以及皮层灵敏度可视化。使用提出的解剖坐标方法在七个神经发育头颅图谱上配准一个探头，每个光纤的平均标准差为2.29毫米，与使用传统2D到3D配准的8.68毫米相比，跨受试者放置变异性减少了约74%。结论：NeuroCaptain v2提供了一个可重复、完全开源的fNIRS探头布局设计工作流程，便于在三维解剖环境中直接进行解剖引导的探头开发和跨受试者配准。

## Abstract
Significance: Accurate and reproducible optode placement is crucial for obtaining high-quality fNIRS data in both individual and group-level neuroimaging studies. Conventional optode/probe montage design tools usually transform a probe layout defined in 2D Cartesian space onto a 3D head surface using a mass-spring model. Such mechanical transformation, combined with the indirect mapping between the 2D probe definition and the 3D target space, can introduce placement variations across different head surfaces and subjects. Aim: We introduce NeuroCaptain v2, an open-source Blender-based add-on designed to enable interactive, anatomically guided optode design, registration, and cortical sensitivity visualization for fNIRS head-cap and probe creation. Approach: NeuroCaptain v2 enables researchers to add, move, and edit fNIRS sources and detectors directly over a 3D head surface mesh, defining anchored optode positions, as well as setting the stiffness of the springs between adjacent optodes. It then utilizes a built-in Blender physical simulation engine to relax the initial probe layout to satisfy the mechanical constraints. With the built-in mesh-based Monte Carlo (MMC) and diffusion-solver Redbird, NeuroCaptain v2 computes and renders 3D sensitivity maps to guide iterative optode adjustment. The resulting 3D optode layout is stored in the form of barycentric coordinates defined in a 10-20 landmark mesh, enabling consistent probe transfer across different head models. Results: We demonstrate interactive 3D montage design, cross-head-atlas probe registration, and cortical sensitivity visualization across multiple head geometries. Registering a probe across seven Neurodevelopmental head atlases, the proposed anatomical-coordinate approach yields a mean per-optode standard deviation of 2.29 mm, a roughly 74% reduction in cross-subject placement variability compared to 8.68 mm using a conventional 2D-to-3D registration. Conclusions: NeuroCaptain v2 provides a reproducible, fully open-source workflow for fNIRS probe montage design that facilitates anatomically guided probe development and cross-subject registration directly in a three-dimensional anatomical environment.

---

## 论文详细总结（自动生成）

# 中文总结

## 1. 论文的核心问题与整体含义（研究动机和背景）
- **研究动机**：功能性近红外光谱（fNIRS）研究中，光纤（optode）和探头布局的准确性与可重复性对数据质量至关重要。传统方法通常先在二维笛卡尔空间中定义探头布局，再利用质量-弹簧模型机械地映射到三维头部表面。这种间接映射和机械变换在不同头部表面和受试者之间引入了严重的放置变异，降低了跨被试和跨研究的可重复性。
- **整体含义**：提出一种直接在三维解剖环境中交互式设计、配准和评估fNIRS探头布局的开放平台，以提升布局的解剖引导性和跨个体/跨图谱的一致性。

## 2. 论文提出的方法论
- **核心思想**：基于Blender开源3D建模软件，开发NeuroCaptain v2插件，允许用户在三维头部表面网格上直接添加、移动和编辑光源与探测器，并利用Blender内置物理模拟引擎松弛布局以满足机械约束。布局以10-20标志网格中的重心坐标存储，支持跨不同头部模型的精确转移。结合蒙特卡洛（MMC）和扩散求解器Redbird计算三维灵敏度图，指导迭代优化。
- **关键技术细节**：
  - 直接在3D头表面网格上操作，定义锚定光纤位置和相邻光纤间弹簧刚度。
  - Blender物理引擎松弛初始布局，模拟真实头帽张力。
  - 内置MMC和Redbird计算皮层灵敏度，实现可视化。
  - 布局存储为10-20标志网格的**重心坐标**，保证跨模型一致性。
- **算法流程**（文字描述）：
  1. 加载三维头部表面网格（如MRI重建）。
  2. 用户交互放置光源/探测器，设置锚点与弹簧参数。
  3. 运行物理模拟松弛布局，调整光纤位置。
  4. 计算灵敏度图，反馈调整。
  5. 保存布局为10-20标志网格重心坐标，可用于配准到新头部。

## 3. 实验设计
- **数据集/场景**：使用七个**神经发育头颅图谱**（Neurodevelopmental head atlases）作为不同头部几何模型。
- **Benchmark**：采用传统2D到3D配准方法（未具体说明方法名称）作为对比基线。
- **对比方法**：仅对比了“传统2D-to-3D registration”，未具体指明是否代表某一标准工具（如AtlasViewer或SPM中的方法）。实验在7个图谱上配准同一个探头布局，比较每个光纤位置的标准差。

## 4. 资源与算力
- **未提及**：论文摘要和元数据中未说明使用的GPU型号、数量、训练时长或任何计算资源。因此无法总结。

## 5. 实验数量与充分性
- **实验数量**：仅一组定量对比实验：在7个头颅图谱上配准一个探头，测量每个光纤位置的标准差。
- **充分性评估**：
  - **优点**：使用了多个不同几何形状的图谱，体现了跨被试变异的评估。
  - **不足**：仅测试了一个探头布局，未在不同光纤数量、不同头帽类型或真实物理头帽上验证；未进行组级fNIRS数据分析验证布局带来的信号质量提升；缺乏与其他开源工具（如ATLAS、Viewer或FieldTrip）的详细对比。因此实验覆盖面有限，但鉴于论文技术开发性质，初步验证可接受。结果客观展示了变异降低74%。

## 6. 论文的主要结论与发现
- **主要结论**：NeuroCaptain v2实现了可重复、完全开源的fNIRS探头布局设计工作流，允许在三维解剖环境中直接进行解剖引导的探头开发和跨受试者配准。
- **关键发现**：使用新方法（基于10-20网格重心坐标）在7个神经发育图谱上配准，每个光纤的平均标准差为2.29 mm，而传统2D到3D方法为8.68 mm，跨受试者放置变异性减少了约74%。

## 7. 优点
- **直接3D交互**：摆脱传统2D to 3D映射，降低变异。
- **物理模拟**：利用Blender内置引擎模拟弹簧张紧，更贴近真实头帽形变。
- **解剖坐标存储**：以10-20标志网格的重心坐标存储布局，天然支持跨被试配准，且与fNIRS主流坐标系统兼容。
- **开放与集成**：基于开源Blender平台，插件完全开源；同时集成了MMC和Redbird灵敏度求解器，一站式完成设计、配准、灵敏度可视化。
- **定量优势**：跨被试标准差降低74%，可重复性显著提高。

## 8. 不足与局限
- **实验覆盖不足**：仅在一个探头布局上验证，未评估不同布局、不同被试群体（成人/儿童/患者）的鲁棒性。
- **对比方法单一**：传统2D-to-3D方法的具体实现细节未提供，可能不是当前最先进方法（如基于atlas的配准）；缺乏与主流fNIRS布局工具（如AtlasViewer的PROBESET、FieldTrip的布局函数）的对比。
- **计算资源未报告**：缺少物理模拟和MMC计算的耗时或资源需求，实践者可参考性降低。
- **应用限制**：依赖高质量三维头部表面网格（需从MRI或模板获得），对于仅有颅骨电极坐标的临床场景可能不适用；未讨论fNIRS光纤与EEG电极的联合布局。
- **无组级信号验证**：未通过实际fNIRS数据（如激活对比）证明布局变异降低能直接提升统计功效或效应量。

（完）
