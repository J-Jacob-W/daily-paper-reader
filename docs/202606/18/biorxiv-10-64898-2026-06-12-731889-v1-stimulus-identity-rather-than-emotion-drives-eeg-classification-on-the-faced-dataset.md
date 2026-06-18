---
title: Stimulus identity rather than emotion drives EEG classification on the FACED dataset
title_zh: 刺激身份而非情绪驱动FACED数据集上的EEG分类
authors: "Gerster, M., Sirotina, E., Orlovskii, A., Hertz, A., Champaud, J., Guarino, D., Tulli, S."
date: 2026-06-16
pdf: "https://www.biorxiv.org/content/10.64898/2026.06.12.731889v1.full.pdf"
tags: ["query:eeg-ode-ln"]
score: 10.0
evidence: 基于EEG的情绪识别数据集分析揭示刺激身份混淆
tldr: FACED数据集的EEG情感分类主要反映刺激身份而非情感。使用线性SVC和CLISA模型分析发现：(1)被试报告感受到与未感受到指定情感时分类性能相当；(2)用自报告标签替换刺激标签后准确率下降；(3)减少到每种情感一个视频时准确率反而提升。这些结果源于数据集每类刺激少、使用刺激标签及基于视频内时间分割的交叉验证。研究提出五点建议，包括增加刺激多样性、保证时间独立性、验证标签有效性等，以避免刺激身份混淆。
source: biorxiv
selection_source: fresh_fetch
motivation: 揭示FACED数据集中刺激身份混淆问题，指出其设计缺陷影响情感解码可靠性。
method: 使用LinearSVC和CLISA模型，通过对比刺激标签与自报告标签、不同视频数量下的分类性能。
result: 分类性能主要来自刺激身份而非情感；自报告标签准确率降低；减少视频后准确率上升。
conclusion: 提出五点建议指导未来情感EEG研究设计，避免刺激身份混淆。
---

## 摘要
可靠的基准数据集对于推进基于脑电图的情绪识别至关重要。细粒度情感计算脑电图数据集（FACED）是最大的公开可用脑电图情绪数据集（123名受试者，九种情绪类别），也是一个广泛采用的基准。我们证明，FACED上的受试者内和跨受试者分类主要反映的是刺激身份而非情绪。使用线性分类器（LinearSVC）和深度学习模型（CLISA），我们显示：（1）在受试者报告感受到与未感受到指定情绪的条件下，分类性能相当；（2）当用个体自我报告替换刺激分配标签时，准确率下降；（3）当将每个情绪减少到一个视频时，尽管丢弃了三分之二的数据，准确率却提高了。这些结果反映了FACED中的三个设计选择：每个类别刺激数量少、刺激分配标签以及交叉验证中采用视频内时间分割。这些因素共同使得数据集容易受到时间自相关和刺激身份混淆的影响。为指导未来工作，我们提出五项建议——涵盖刺激多样性、时间独立性和标签验证——用于减少这些混淆的情绪解码研究设计。

## Abstract
Reliable benchmark datasets are critical for advancing EEG-based emotion recognition. The Finer-grained Affective Computing EEG Dataset (FACED) is the largest publicly available EEG emotion dataset (123 subjects, nine emotion categories) and a widely adopted benchmark. We demonstrate that both intra-subject and cross-subject classification on FACED primarily reflects stimulus identity rather than emotion. Using a linear classifier (LinearSVC) and a deep learning model (CLISA), we show that (1) classification performance is comparable for trials where subjects reported feeling versus not feeling the assigned emotion; (2) accuracy drops when stimulus-assigned labels are replaced with individual self-reports; and (3) accuracy increases when reducing to one video per emotion despite discarding two-thirds of the data. These results reflect three design choices in FACED: few stimuli per category, stimulus-assigned labels, and within-video temporal splits for cross-validation. Together, these make the dataset susceptible to temporal autocorrelation and stimulus-identity confounds. To guide future work, we propose five recommendations -- spanning stimulus diversity, temporal independence, and label validation -- for emotion-decoding study designs that mitigate these confounds.

---

## 论文详细总结（自动生成）

### 1. 论文的核心问题与整体含义（研究动机和背景）
- **核心问题**：FACED（Finest-grained Affective Computing EEG Dataset）是目前最大的公开EEG情绪数据集（123名被试，9类情绪），已被广泛用作基准。但本研究证明，在该数据集上进行受试者内和跨受试者分类时，分类器主要学习的是**刺激身份**（即具体哪一个视频）而非真正的情绪状态。这一混淆源于数据集的三个设计选择：每类情绪仅有少量视频（3~4个）、使用刺激指派的标签（而非被试自报告）、以及采用视频内时间分割的交叉验证（训练与测试取自同一视频的不同时间片段），导致时间自相关和刺激身份可被模型利用。
- **整体含义**：基于FACED的EEG情绪识别方法（包括许多近期深度学习方法）实际评估的可能是“刺激识别”而非“情绪识别”。该发现对依赖该数据集的基准工具（如TorchEEG、Meta NeuralBench）提出了警示，并呼吁改进实验设计以避免混淆。

### 2. 论文提出的方法论：核心思想、关键技术细节、算法流程
- **核心思想**：通过对比不同标签来源（刺激标签 vs 被试自报告）、不同刺激数量（全视频 vs 每类情绪仅留一个视频）、以及模型预测在一致/不一致试验上的表现，来识别混淆因素是刺激身份还是情绪。
- **关键技术细节**：
  - 使用官方预计算的**差分熵（DE）特征**，5个频带（δ, θ, α, β, γ）× 30通道，1秒非重叠窗口，每试验30个窗口。预处理包括运行归一化（指数衰减率0.990）和线性动力学系统（LDS）平滑。
  - 分类器：**LinearSVC**（线性支持向量分类器）和**CLISA**（对比学习跨主体对齐的深度学习模型，默认超参数）。
  - 受试者内实验：10折交叉验证，每折将视频的最后30秒分割为27秒训练、3秒测试（同一视频内时间分割）。
  - 跨受试者实验：10折逐被试交叉验证（训练集和测试集来自不同被试）。
  - 自报告标签：被试看完视频后对8种非中性情绪（0-7量表）打分，以最高分项作为该被试对该视频的“主导情绪”。
  - 一致性分析：将试验分为“一致”（被试主导情绪与刺激标签相同）和“不一致”（不同），分别计算准确率。
  - 单视频实验：仅保留每类情绪的第一个视频（9个视频），丢弃2/3数据，重复上述流程。
- **算法流程**（文字说明）：
  1. 提取DE特征（150维/窗口），按被试归一化+LDS平滑。
  2. 受试者内：对每个被试，将每个视频的30秒等分为10个片段，9段训练、1段测试（保持时间顺序）；使用LinearSVC，C通过测试片段上的准确率选择（乐观偏倚，为忠实复现保留）。
  3. 跨受试者：将所有被试分为10折，每折训练集包含123-12或123-15个被试，测试集为剩余；同样C通过测试折准确率选择（2d中使用嵌套5折交叉验证纠正偏倚）。
  4. 对于自报告标签实验，将训练/测试标签替换为被试自报告主导情绪（8类）。
  5. 对于单视频实验，仅选取每个情绪的第一个视频的EEG数据进行相同训练/测试。

### 3. 实验设计：数据集、基准、对比方法
- **数据集**：FACED（123名被试，32通道EEG，28个视频，9类情绪：愤怒、厌恶、恐惧、悲伤、中性、娱乐、灵感、喜悦、温柔）。非中性每类3个视频，中性4个视频。分析使用最后30秒的DE特征。
- **基准**：原始论文（Chen et al., 2023）报道的LinearSVC受试者内准确率51.1%，跨受试者准确率35.2%；CLISA跨受试者准确率42.35%。
- **对比方法**：本研究复现基线（LinearSVC和CLISA），并比较以下变体：
  - 刺激标签 vs 自报告标签
  - 全视频（28个） vs 每类单视频（9个）
  - 一致试验 vs 不一致试验（基于自报告）
  - 无嵌套CV（乐观偏倚） vs 嵌套CV（仅2d）
  - 线性分类器（LinearSVC） vs 深度学习模型（CLISA）

### 4. 资源与算力
- **文中未明确说明使用的GPU型号、数量和训练时长**。仅指出CLISA使用了公开实现和默认超参数，LinearSVC为CPU可执行。对计算资源无具体描述。

### 5. 实验数量与充分性
- **实验数量**：共实施了7组主要实验（1a, 1b, 2a, 2b, 2c, 2d, 2e），其中2b和2c还包含子分析（一致/不一致分裂）。此外，2e复现了2a-2d用CLISA的全部跨被试实验。实验设计完整，覆盖了关键变量（标签来源、刺激多样性、时间分割、模型复杂度）。
- **充分性与公平性**：
  - 实验设计具有针对性，有效揭示了混淆。
  - 作者承认了乐观偏倚（2a和1a中C选择泄露测试集）并复现了该做法以忠实于原始方法；2d中使用了嵌套CV纠正，结果依然支持结论。
  - 对CLISA的复现准确率（34.2%）低于原始报道（42.35%），但混淆模式一致，不影响主要结论。
  - 局限性：仅分析一种特征（DE），两种模型，一个数据集；因此推广性需进一步验证。

### 6. 论文的主要结论与发现
- **主要结论**：FACED上的EEG情绪分类主要反映刺激身份而非情绪。
- **具体证据**：
  - 受试者内基线58.8%，但单视频后升至71.3%（使用更少数据，准确率反升）。
  - 跨被试基线39.4%，一致与不一致试验准确率接近（33.9% vs 36.0%），说明分类器不依赖于被试是否实际感受了该情绪。
  - 用自报告标签替换后准确率降至26.8%，且在不一致试验上仅15.3%（接近随机12.5%），表明分类器无法预测与刺激标签不同的自报告情绪。
  - 单视频跨被试准确率升至44.9%（使用1/3数据），说明额外的视频并未提供情绪信号，反而稀释了刺激身份混淆。
- **模型无关性**：CLISA也表现出相同模式，说明混淆并非线性模型特有。
- **根本原因**：三类设计缺陷——每类刺激数太少（3个）、使用刺激标签而非自报告、视频内时间分割交叉验证（训练与测试取自同一视频的不同时间点，利用时间自相关）。此外，预处理中的LDS平滑和归一化也是在整个记录会话上计算，存在数据泄漏。

### 7. 优点
- **方法严谨**：通过多个对比实验（单视频、标签替换、一致性分析）系统性地剥离混淆因素，论证充分。
- **透明度高**：公开分析代码（GitHub），使用官方数据与特征，便于复现和验证。
- **复现并讨论偏差**：复现基线时略微高于原文，并诚实指出CLISA复现差异，未回避矛盾。
- **提出实用建议**：基于结果给出了五条具体可操作的建议（确保时间独立性、使用大量刺激、个性化刺激、收集自报告验证、引入多模态测量），对领域有明确指导意义。
- **承认数据集的贡献**：虽然指出缺陷，但认为FACED开放共享的做法是重大贡献，并鼓励后续自我纠正。

### 8. 不足与局限
- **实验覆盖有限**：仅使用DE特征和两种分类器（LinearSVC和CLISA），其他特征（如功率谱、功能连接）和更先进模型（Transformer、大型预训练模型）未测试，结论的泛化性需进一步验证。
- **自报告标签的噪声**：自我报告可能受需求特征、述情障碍、任务参与度等影响，本身不是金标准；无中性情绪自报告项，处理方式可能引入偏差。
- **时间自相关来源未区分**：无法分离内在EEG自相关（如西瓜实验所示）与刺激驱动自相关（自然视频的1/f时间结构），但无论如何都构成混淆。
- **CLISA复现差异未解释**：未能重现原文42.35%，可能影响对深度学习绝对性能的评估，但混淆模式一致性支持核心论点。
- **利益冲突**：所有作者受雇于HABS公司（开发情感计算技术），虽声明使用公开数据，但可能存在潜在偏向。
- **仅分析九分类任务**：未涉及原文中的二分类（中性 vs 情绪），尽管文中提及该设置每类有12个刺激，混淆可能部分稀释但未验证。

（完）
