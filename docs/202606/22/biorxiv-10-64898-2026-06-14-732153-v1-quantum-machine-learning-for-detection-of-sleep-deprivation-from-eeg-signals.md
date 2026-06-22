---
title: Quantum machine learning for detection of sleep deprivation from EEG signals
title_zh: 基于量子机器学习的脑电图信号睡眠剥夺检测
authors: "Sarma-Sarkar, P., Saini, R., Roy, P. P."
date: 2026-06-18
pdf: "https://www.biorxiv.org/content/10.64898/2026.06.14.732153v1.full.pdf"
tags: ["query:eeg-ode-ln"]
score: 9.0
evidence: 基于量子机器学习的EEG信号解码用于睡眠剥夺检测
tldr: "睡眠剥夺影响半数印度人口，EEG能客观反映神经变化。本研究使用量子支持向量机（QSVM）和混合量子神经网络（HQNN），提取频谱功率、Hjorth参数及功能连接等特征并编码为量子态进行分类。在epoch级评估中，HQNN准确率达96.88%，subject级为81.25%，均优于此前最佳结果。结果表明量子机器学习为EEG睡眠剥夺检测提供了有竞争力的新方案。"
source: biorxiv
selection_source: fresh_fetch
motivation: 睡眠剥夺普遍有害，需开发基于EEG的自动检测方法。
method: 采用QSVM和HQNN，利用频谱功率、Hjorth参数及功能连接特征，编码为量子态构建量子核。
result: "HQNN在epoch级准确率96.88%，subject级81.25%；QSVM分别为93.75%和75.00%，均超越先前。"
conclusion: 量子机器学习在EEG睡眠剥夺检测中展现潜力，可推动实际生物医学应用。
---

## 摘要
据估计，印度约有50%的人口经历过睡眠相关障碍。睡眠剥夺是一种常见状况，会对认知表现、神经功能和整体健康产生不利影响。脑电图（EEG）提供了一种客观手段来捕捉与睡眠缺失相关的神经变化，因此非常适合自动化检测框架。在本研究中，我们探索应用量子支持向量机和混合量子神经网络，利用静息态脑电信号对睡眠剥夺和休息良好状态进行分类。

我们采用了一套全面的特征提取流程，包括频谱带功率、频带比率、Hjorth参数和功能连接性度量。这些特征随后被编码为量子态以构建量子核，并用于分类。模型性能在epoch级别和受试者级别两种数据划分方案下进行评估。

混合量子神经网络（HQNN）在两种评估设置下均取得最高性能，在epoch级别达到96.88%的准确率，在受试者级别达到81.25%的准确率。QSVM模型在epoch级别和受试者级别评估中分别达到93.75%和75.00%的准确率。在受试者级别和epoch级别评估中，HQNN优于先前报告的结果（68.23%和95.72%）。总体而言，这些发现突显了量子机器学习作为基于EEG的睡眠剥夺检测的一种有竞争力方法的潜力，对现实世界的生物医学应用具有前景。

## Abstract
Approximately 50% of the population in India is estimated to experience sleep-related disorders. Sleep deprivation is a prevalent condition that adversely impacts cognitive performance, neural functioning, and overall health. Electroencephalography (EEG) offers an objective means of capturing neural alterations associated with sleep loss, making it well-suited for automated detection frameworks. In this study, we explore the application of a Quantum Support Vector Machine and Hybrid Quantum Neural Networks to classify sleep-deprived and well-rested states using resting-state EEG signals.

A comprehensive feature extraction pipeline is employed, incorporating spectral band power, band ratios, Hjorth parameters, and functional connectivity measures. These features are subsequently encoded into quantum states to construct a quantum kernel, which is then utilized for classification. Model performance is evaluated under both epoch-level and subject-level data partitioning schemes.

The Hybrid Quantum Neural Network (HQNN) achieves the highest performance across both evaluation settings, attaining an accuracy of 96.88% at the epoch level and 81.25% at the subject level. The QSVM model achieves accuracies of 93.75% and 75.00% for epoch-level and subject-level evaluations, respectively. At subject-level and epoch -level evaluation, HQNN outperforms previously reported results (68.23% and 95.72%). Overall, these findings highlight the potential of quantum machine learning as a competitive approach for EEG-based sleep deprivation detection, with promising implications for real-world biomedical applications.

---

## 论文详细总结（自动生成）

## 基于量子机器学习的脑电图信号睡眠剥夺检测：论文总结

### 1. 论文的核心问题与整体含义（研究动机和背景）
- **背景**：睡眠剥夺是全球性公共卫生问题，影响认知、安全与健康。印度约50%人口存在睡眠相关障碍。现有检测方法依赖主观报告或实验室评估，难以实时应用。
- **问题**：如何利用静息态脑电图（EEG）客观、自动地检测急性睡眠剥夺状态。
- **动机**：传统机器学习（如SVM、随机森林、CNN）已在EEG分类中取得较好效果，但量子机器学习（QML）凭借叠加态、纠缠等特性，有望在更高维特征空间中捕捉更复杂的神经模式。本研究首次将QML应用于EEG睡眠剥夺检测。

### 2. 论文提出的方法论：核心思想、关键技术细节
- **核心思想**：将EEG特征提取后编码为量子态，利用量子核（QSVM）或可训练量子电路（HQNN）进行二分类（正常睡眠 vs. 睡眠剥夺）。
- **特征提取管道**：
  - 预处理：0.2–45 Hz带通滤波、重采样至256 Hz、平均参考、20秒非重叠epoch、峰值–峰值振幅≥500 μV的epoch剔除。
  - 特征：各导联绝对/相对δ、θ、α、β频带功率；θ/α与β/α比值；特定电极（Fp1, Fp2, Fpz, Fz, Cz, Pz, Oz）的Hjorth参数（活动性、移动性、复杂度）；前额θ波平均振幅调制（Hilbert包络）；6个电极（Fz, Cz, Pz, Oz, T7, T8）对的β频带相干性平均值。
- **特征降维与标准化**：使用ANOVA F统计选取最高分的32个特征（对应5量子位），并作L2归一化（振幅编码要求向量模为1）。若特征不足32则补零。
- **QSVM**：
  - 将每个样本编码为n量子位的振幅态（n=2-5，对应4/8/16/32维特征）。
  - 核函数：\( k(\mathbf{x}_1, \mathbf{x}_2) = |\langle\phi(\mathbf{x}_1)|\phi(\mathbf{x}_2)\rangle|^2 \)，通过量子电路实现：振幅编码+逆编码，测量全|0>态概率。
  - 预计算训练核矩阵和测试核矩阵，用标准SVM（precomputed kernel）训练。
- **HQNN（混合量子神经网络）**：
  - 特征先经全连接层降维至n维（n=量子位数），tanh激活。
  - 角度编码：每个维度的值作为旋转角作用于相应量子比特的RY门。
  - 可训练量子层：多层强纠缠层（单量子比特旋转+CNOT纠缠），层数1-3。
  - 测量每个量子比特的Pauli-Z期望值，得到n维观测向量。
  - 再经全连接层+ sigmoid输出睡眠剥夺概率。
  - 训练：二元交叉熵损失，Adam优化器，早停（patience=3）。

### 3. 实验设计：数据集、基准、对比方法
- **数据集**：Xiang et al. (2024) 的71名健康受试者（17-23岁，37男34女），每人两次记录（正常睡眠NS与睡眠剥夺SD，间隔7天-1个月），61导电极，500Hz采样，5分钟睁眼静息态。
- **预处理后**：共1661个无伪影epoch（20秒）。
- **划分策略**：
  - **epoch级别**：随机划分训练/测试（约2/3训练，1/3测试），可能有同受试者epoch同时出现在训练和测试集。
  - **受试者级别**：按受试者划分，保证同一受试者所有epoch全在训练或测试集，更具泛化性。
- **基准基准**：Kumar et al. (2025) 在同一数据集上的经典方法结果（随机森林、LightGBM、XGBoost、SVC、CNN、LSTM、Transformer）。最优epoch级：CNN 95.72%；subject级：RF 68.23%。
- **对比方法**：QSVM（不同量子位数2-5、样本数100/200/400、归一化方式MinMax/Standard）和HQNN（同样变量+学习率0.1/0.01/0.001、量子层数1-3）。另设经典SVM（线性核、RBF核）作为基线（表里未明确列出，但文中有提及）。
- **评估指标**：准确率、精确率、召回率、F1分数。

### 4. 资源与算力
- 论文未明确说明使用的GPU型号、数量或训练耗时。
- 提到量子核计算成本随样本数平方增长，因此在模拟器上只使用子集（100/200/400个epoch），且部分实验（尤其是100 epoch）得到最佳结果，暗示受算力约束。
- 所有量子电路在经典模拟器（如PennyLane/Qiskit）上执行，未在真实量子硬件上运行。

### 5. 实验数量与充分性
- **实验数量丰富**：QSVM在4种量子位数×3种样本数×2种归一化=24组；HQNN在同样4×3×3学习率×3层数=108组（但论文只报告了最佳组合，总实验量实际更大）。
- **足够充分**：覆盖不同资源（量子位数）、不同数据规模、不同预处理；epoch与subject两种划分；对比了经典SVM（文中提到但未详列）。消融实验体现在量子位数、样本数、归一化、学习率、层数等。
- **客观性**：固定随机种子（seed=11），确保可复现。质量感知子采样（优先选取清洁epoch）避免随机偏差。
- **不足**：由于算力限制，仅使用最多400个epoch（占全部1661的24%），可能未充分展示大样本下性能。受试者级别仅1次划分（无交叉验证），结果波动可能较大。

### 6. 论文的主要结论与发现
- **HQNN表现最优**：epoch级别准确率96.88%（4量子位，100epoch，LR=0.1，3层），受试者级别准确率81.25%（3量子位，100epoch，LR=0.01，3层）。
- **QSVM其次**：epoch级别93.75%（4量子位，100epoch，MinMax归一化），受试者级别75.00%（5量子位，100epoch，Standard归一化）。
- **超越经典方法**：所有QML模型在受试者级别均超过经典SVC（65.08%）及之前最佳RF（68.23%）；HQNN epoch级也超过CNN（95.72%）。表明QML在泛化和分类性能上具有竞争力。
- **量子位数的影响**：4量子位在多数设置下最佳；更高量子位（5）未见一致优势，可能因特征维度限制或噪声。
- **样本数影响**：100 epoch结果最佳，更大样本（400）性能下降，可能因量子核计算精度或特征选择不匹配。

### 7. 优点：方法或实验设计上的亮点
- **开创性**：首次将量子机器学习应用于EEG睡眠剥夺检测，填补领域空白。
- **细致的特征工程**：结合频谱、时间域、功能连接多维度特征，并采用生理学依据的电极选择（如Hjorth参数仅用额顶电极、相干用跨脑区电极）。
- **系统参数探索**：对量子位数、样本大小、归一化、学习率、层数进行网格搜索，客观评估资源-性能权衡。
- **两种数据划分**：epoch级和subject级评估，提供了对内一致性和跨受试者泛化的全面比较。
- **质量感知子采样**：基于峰值–峰值振幅选取清洁epoch，减少噪声干扰。
- **结果可复现**：固定随机种子，代码和流程透明。

### 8. 不足与局限
- **数据集规模小**：仅71人，可能不足以代表人群多样性，且subject级划分后训练集更小，统计稳定性有限。
- **模拟环境而非真实量子硬件**：未考虑实际量子噪声、退相干和门误差，性能在真实设备上可能下降。
- **计算瓶颈**：量子核矩阵的计算复杂度为O(N²)，限制了可用样本数（最多400），无法与使用全数据集的经典方法公平比较。
- **特征降维隐患**：ANOVA选择top 32特征可能丢弃其他有用信息；振幅编码要求严格归一化可能损失幅度信息。
- **受试者级别性能仍偏低**：81.25%距离实际应用（>90%）仍有差距，且仅一次划分，缺乏交叉验证，结果可能波动。
- **未做统计显著性检验**：未报告置信区间或P值，仅给出单次结果与经典方法均值比较。
- **缺乏多分类或多模态扩展**：仅二分类，未探索多水平睡眠剥夺或结合其他生理信号。
- **可解释性不足**：量子电路内部变换难以直接可视化，无法明确哪些频带或区域贡献最大。

（完）
