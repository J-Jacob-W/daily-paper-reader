---
title: EEG-based classification models reveal differential neural processing of words and images
title_zh: 基于EEG的分类模型揭示词语和图像的差异神经处理
authors: "Morakabati, N. R., Thiha, A. S., Schechtman, E."
date: 2026-06-15
pdf: "https://www.biorxiv.org/content/10.64898/2026.03.16.712233v3.full.pdf"
tags: ["query:eeg-ode-ln"]
score: 9.0
evidence: 基于脑电图的分类模型，使用机器学习解码词汇和图像的神经处理
tldr: 本研究利用EEG和SVM分类器，探究了5类物体（动物、工具、食物、场景、车辆）在图片和单词刺激下的神经表征差异。结果显示图片比单词分类准确率更高，所有类别对均可区分，而单词仅一对可区分；顶叶和左颞电极贡献更大。该方法验证了EEG在类别解码中的效用，为研究清醒及离线状态下语义表征的动态提供了有效工具。
source: biorxiv
selection_source: fresh_fetch
motivation: 开发基于EEG的机器学习方法，以区分不同语义类别（图片vs.单词）的神经加工模式。
method: 30名被试完成同类连续反应任务，记录EEG，使用支持向量机（SVM）进行个体内分类。
result: 图片分类准确率显著高于单词；图片所有类别对可区分，单词仅一对；顶叶和左颞电极贡献更大。
conclusion: EEG结合SVM可有效解码类别水平神经表征，尤其适用于图片刺激，有助于探索语义加工的神经机制。
---

## 摘要
背景采用神经影像数据的机器学习方法对于监测神经表征的激活非常有用。具体来说，它们可以用于识别参与处理特定类别项目的大脑网络。该方法已被应用于神经影像数据，包括功能性磁共振成像数据和脑电图数据。新方法本文提出了一种利用脑电图研究类别表征的任务和分析流程。参与者（N=30）观看了一系列属于五个类别（动物、工具、食物、场景和车辆）的物品图像和词语，并在连续呈现同一类别的项目时做出反应。结果我们在参与者内部的脑电图数据上训练了支持向量机，发现图像试验和词语试验均产生了显著的类别分类准确率，其中图像试验的准确率高于词语试验。在以成对方式比较类别时，图像试验中所有类别对在统计上均可区分，而词语试验中只有一对可区分。顶叶和左颞电极对图像分类的贡献大于额叶和右颞电极。类别特异性活动模式在图像试验中也跨参与者泛化。与现有方法的比较我们的数据和分析流程产生了较高的分类准确率，主要针对图像试验，为脑电图数据在神经解码中的实用性提供了支持。结论这些方法有助于探索清醒状态下以及可能离线状态下类别水平神经表征的激活和再激活。

## Abstract
BackgroundMachine learning methods employing neuroimaging data are useful for monitoring the activation of neural representations. Specifically, they can be used to discern the brain networks engaged in processing specific categories of items. This approach has been employed on neuroimaging data, including functional magnetic resonance imaging data and electroencephalography (EEG) data.

New methodHere, we present a task and an analytical pipeline for investigating category representations using EEG. Participants (N = 30) viewed a series of images and words of objects belonging to five categories (Animals, Tools, Food, Scenes, and Vehicles) and responded when items from the same category were presented consecutively.

ResultsWe trained support vector machines on EEG data within participants and found that both image trials and word trials yielded significant category classification accuracy, with image trials achieving higher accuracy than word trials. When comparing categories in a pair-wise fashion, all pairs were statistically distinguishable for image trials, whereas only one pair was distinguishable for word trials. Parietal and Left Temporal electrodes contributed more to image classification than Frontal and Right Temporal electrodes. Category-specific activity patterns also generalized across participants for image trials.

Comparison with existing methodsOur data and analytic pipeline yielded high classification accuracies, primarily for image trials, providing support for the utility of EEG data for neural decoding.

ConclusionsThese methods can be instrumental for exploring the activation and reactivation of neural representations at the category level during wakefulness and, potentially, during offline states.

---

## 论文详细总结（自动生成）

## 1. 论文的核心问题与整体含义（研究动机和背景）
- **核心问题**：不同类型（如图片 vs. 词语）的语义类别信息在脑电（EEG）信号中是否可解码？其神经表征在时间、空间和跨个体上的差异如何？
- **研究动机**：传统事件相关电位（ERP）方法受限于单电极、特定时间窗口，难以捕捉分布式、动态的神经模式。机器学习方法能够从全头皮电极的多维时域信号中提取类别信息，为研究语义加工提供新工具。
- **整体意义**：验证高密度EEG结合支持向量机（SVM）在类别水平神经解码上的可行性，为后续研究清醒及离线状态（如睡眠）下语义表征的动态变化奠定方法学基础。

## 2. 论文提出的方法论：核心思想、关键技术细节、算法流程
- **核心思想**：利用SVM从EEG时域数据中解码呈现刺激的语义类别（五类：动物、工具、食物、场景、车辆）和模态（图片 vs. 词语）。
- **技术细节**：
  - 数据预处理：0.3-35 Hz带通滤波，重参考至乳突电极平均，ICA去伪迹，分段为刺激前1.25s至后2.75s。
  - 特征构建：每个试验取182个时间点（间隔22ms），每个时间点使用58个头皮电极的电压值作为特征。
  - 分类器：线性核SVM（MATLAB `fitcecoc`，默认参数，无超参数调优），采用5折交叉验证，重复20次随机重排。
  - 统计检验：基于簇的置换检验（1000次置换），控制多重比较。
- **算法流程**：
  1. 对每个被试、每个时间点训练一个SVM（one-vs-all）。
  2. 计算准确率，平滑（62ms窗口 + 后续9个时间点因果平滑）。
  3. 通过置换检验识别显著高于机遇水平（1/5）的连续时间簇。

## 3. 实验设计：数据集、场景、基准与对比方法
- **数据集**：自行采集的EEG数据（30名被试），100个刺激（50张图片+50个词语），每类10个图片+10个词语。来源：THINGS数据库、BOLD5000数据库等。
- **任务范式**：被试观看交替呈现的图片或词语，当连续两个刺激属于同一类别时按空格键（catch trials），以保证注意力。
- **基准**：机遇水平准确率（5类=0.2，二分类=0.5）。
- **对比方法**：只采用SVM在同一框架内比较不同条件（图片 vs. 词语；不同电极组；跨被试泛化等），未与其他机器学习方法或ERP分析进行直接对比。

## 4. 资源与算力
- 文中**未提及**使用的GPU型号、数量或训练时长。所有模型在MATLAB中运行，基于CPU即可完成（单被试SVM训练量不大）。未说明计算设备细节。

## 5. 实验数量与充分性
- **实验组数量**：
  - 主分析：全类别分类（图片+词语混合）、模态分类（图片 vs. 词语）、单模态内类别分类（图片、词语分别）。
  - 控制分析：排除重复项目、排除前次试验影响、排除catch/response邻近效应。
  - 成对类别比较：5类共10对 × 两种模态。
  - 电极区域分析：4个脑区 × 2种模态，左右半球对比，单电极分析。
  - 跨被试分类：leave-one-out × 30人。
- **充分性**：实验数量丰富，覆盖了类别、模态、时空、跨个体的多重维度，并包含多项控制分析（如项目特异性、顺序效应），解释充分。但缺少与传统ERP方法的直接对比，也未对SVM与其他分类器（如LDA、神经网络）进行系统比较。

## 6. 论文的主要结论与发现
- 图片和词语刺激均能引发可解码的类别神经活动，但**图片的分类准确率显著高于词语**（图片峰值0.32 vs. 词语峰值0.23，机遇0.2）。
- 图片条件下**所有类别对均能显著区分**；词语条件下仅“动物 vs. 工具”可区分。
- **顶叶**电极贡献最高，额叶最低；**左颞**电极显著优于右颞。
- 类别表征可**跨被试泛化**，但仅对图片显著（准确率仅0.211，接近机遇），提示个体间差异较大。
- 无法实现跨模态泛化（图片训练→词语测试不显著），表明EEG可能更多反映模态特异性加工。

## 7. 优点：方法或实验设计上的亮点
- **任务设计精巧**：交替呈现图片与词语，控制低层视觉特征（词语加抽象背景），匹配频率/长度，并采用catch trial维持注意力。
- **分析流程全面**：涵盖被试内/间、全头皮/局部电极、成对比较、多种控制分析，验证结果稳健性。
- **开源共享**：代码、数据、刺激均公开，可复现。
- **方法学贡献**：证明低密度EEG（单电极）也能在一定程度上解码类别信息，降低了成本门槛。

## 8. 不足与局限：包括实验覆盖、偏差风险、应用限制
- **源定位不明**：EEG头皮分布无法直接对应脑区，无法确定神经起源。
- **零相位滤波导致的时间偏移**：文中承认分类准确率在刺激呈现前已出现，虽通过仅分析刺激后时间缓解，但可能影响早期时窗的解释。
- **跨模态泛化失败**：可能是统计功效不足（词语准确率低），而非真正不存在模态无关表征。
- **样本同质性**：被试以亚裔青年为主，利手和教育背景等未详细控制，可能影响泛化性。
- **缺少方法对比**：未与ERP、时频分析或其他机器学习模型（如LDA、CNN）进行性能比较，无法判断SVM是否最优。
- **效应量小**：跨被试分类准确率仅比机遇高0.011，虽显著但实际应用有限。

（完）
