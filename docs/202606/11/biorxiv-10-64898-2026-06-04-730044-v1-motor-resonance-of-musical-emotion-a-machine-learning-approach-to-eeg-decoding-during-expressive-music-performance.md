---
title: "Motor Resonance of Musical Emotion: A Machine Learning Approach to EEG Decoding During Expressive Music Performance"
title_zh: 音乐情感的动觉共振：表现性音乐表演中脑电解码的机器学习方法
authors: "Proverbio, A. M., milovanovic, m."
date: 2026-06-08
pdf: "https://www.biorxiv.org/content/10.64898/2026.06.04.730044v1.full.pdf"
tags: ["query:eeg-ode-ln"]
score: 9.0
evidence: 钢琴演奏中音乐情绪的EEG解码
tldr: 现有EEG情感研究多基于被动聆听，本研究探索主动演奏时脑电能否解码音乐情感。专业钢琴家演奏六类情感片段，提取theta/alpha/beta频带功率，用机器学习分类。随机森林准确率达0.42（高于随机0.167），加入arousal特征后提升至0.58。结果表明主动表达中的EEG振荡包含可区分的情感信息，拓展了情感神经科学至生态化表演情境。
source: biorxiv
selection_source: fresh_fetch
motivation: 探究主动音乐表达中情感状态的神经动力学，超越被动聆听范式。
method: 单被试记录钢琴家128导EEG，提取节律特征，用SVM、随机森林和梯度提升分类六种情绪。
result: 随机森林准确率0.42，加入arousal特征后达0.58，特征贡献分布广泛。
conclusion: 主动演奏时EEG振荡可解码情感，支持生态化音乐表演研究。
---

## 摘要
理解表现性音乐表演背后的神经动力学仍是神经科学、音乐认知和计算建模交叉领域的一项重大挑战。虽然情感脑电图研究主要关注被动暴露于情感刺激，但主动音乐表达过程中的振荡脑活动研究相对较少。本单被试研究探究了专业音乐会钢琴家在表现性钢琴演奏过程中记录的频带限制脑电图是否包含足够的判别结构，以支持对音乐定义的情感类别进行监督多类分类。

方法：在连续自然主义会话中，一名专业音乐会钢琴家演奏了巴赫、贝多芬和肖邦的情感化片段，同时从128个头皮位点记录脑电图。音乐片段先前根据情感效价、节奏、能量/唤醒度和调性结构进行了分类和感知验证。从连续的脑电图记录中提取了180个不重叠的2秒无伪影片段，每个情感类别30个片段。在选定的中央顶叶和后部电极上计算了θ（3.5-7.5 Hz）、α（7.5-12.5 Hz）和高β（24-30 Hz）频段的平均频谱功率，每个片段得到24个脑电图特征。使用80/20训练-测试分割结合5折交叉验证评估了线性支持向量机、随机森林和梯度提升分类器。

结果：仅基于脑电图的分类在所有模型中均达到高于随机水平的性能，其中随机森林取得了最高准确率（0.42）、宏F1分数（0.414）和Cohen's kappa（0.30），超过了理论随机水平0.167。特征重要性分析显示，θ、α和高β振荡活动在顶叶和枕叶区域有分布式贡献，未发现单一主导神经标记。加入一个额外的二元唤醒相关特征显著提升了随机森林性能（准确率=0.58；宏F1=0.579；kappa=0.50），表明在分类框架内，唤醒组织对类别可分离性贡献显著。

结论：这些发现表明，伴随表达性音乐动作的振荡脑电图包含与情感差异化表演状态相关的可测量统计结构。本研究并非识别离散的情感神经关联，而是提供了表达性运动-声学交互过程中出现的分布式振荡动力学的计算特征描述，将情感脑电图研究从被动感知范式扩展到生态化的音乐表演情境。

## Abstract
Understanding the neural dynamics underlying expressive musical performance remains a major challenge at the intersection of neuroscience, music cognition, and computational modeling. While EEG studies of emotion have largely focused on passive exposure to affective stimuli, comparatively little research has examined oscillatory brain activity during active musical expression. The present single-subject study investigated whether band-limited EEG activity recorded during expressive piano performance by a professional concert pianist contains sufficient discriminative structure to support supervised multi-class classification of musically defined emotional categories.

MethodsEEG was recorded from 128 scalp sites while a professional concert pianist performed emotionally characterized excerpts from Bach, Beethoven, and Chopin in a continuous naturalistic session. Musical excerpts had been previously categorized and perceptually validated according to emotional valence, tempo, energy/arousal, and tonal structure. From the continuous EEG recording, 180 non-overlapping 2-second artifact-free segments were extracted, yielding 30 segments for each emotional category. Mean spectral power was computed within theta (3.5-7.5 Hz), alpha (7.5-12.5 Hz), and high-beta (24-30 Hz) frequency bands across selected centro-parietal and posterior electrodes, resulting in 24 EEG-derived features per segment. Linear Support Vector Machine, Random Forest, and Gradient Boosting classifiers were evaluated using an 80/20 train-test split combined with 5-fold cross-validation.

ResultsEEG-only classification achieved above-chance performance across models, with Random Forest yielding the highest accuracy (0.42), macro F1-score (0.414), and Cohens {kappa} (0.30), exceeding the theoretical chance level of 0.167. Feature importance analysis revealed distributed contributions across theta, alpha, and high-beta oscillatory activity, particularly over parietal and occipital regions, without evidence for a single dominant neural marker. Inclusion of an additional binary arousal-related feature substantially improved Random Forest performance (accuracy = 0.58; macro F1 = 0.579; {kappa} = 0.50), indicating that arousal organization contributed strongly to category separability within the classification framework.

ConclusionsThese findings suggest that oscillatory EEG activity accompanying expressive musical action contains measurable statistical structure associated with emotionally differentiated performance states. Rather than identifying discrete neural correlates of emotion, the present results provide a computational characterization of distributed oscillatory dynamics emerging during expressive motor-acoustic interaction, extending affective EEG research beyond passive perception paradigms toward ecologically grounded musical performance contexts.

---

## 论文详细总结（自动生成）

# 论文详细中文总结

## 1. 论文的核心问题与整体含义

- **研究动机**：现有EEG情感研究大多基于**被动聆听**情感刺激（如音乐、图片），而主动音乐表演中的情感神经动力学尚不清楚。专业表演者通过运动-声学交互表达情感，其脑电振荡活动是否包含可区分的情感信息？这是本研究的核心问题。
- **整体含义**：将情感神经科学从被动感知范式拓展到**生态化的主动表演情境**，验证了在表达性钢琴演奏过程中，EEG频带功率（θ、α、高β）能够解码多种音乐情感类别，支持“动觉共振”假设，即运动系统与情感状态在听觉-运动整合中紧密耦合。

## 2. 论文提出的方法论

- **核心思想**：利用机器学习对专业钢琴家在演奏六类不同情感音乐片段时的EEG频带功率进行监督分类，检验振荡活动是否含有情感相关的判别结构。
- **关键技术细节**：
  - **EEG记录**：128导联头皮电极，连续自然主义会话。
  - **数据预处理**：从连续EEG中提取180个不重叠的2秒无伪影片段（每类情感30个片段）。
  - **特征提取**：在选定的中央顶叶和后部电极上计算三个频段的平均频谱功率：θ (3.5–7.5 Hz)、α (7.5–12.5 Hz)、高β (24–30 Hz)，共得到**24个特征**（每导联×频段组合）。
  - **分类器**：线性支持向量机 (SVM)、随机森林 (RF)、梯度提升 (GB) —— 使用80/20训练-测试分割结合5折交叉验证。
  - **附加特征**：额外引入一个二元唤醒相关特征（基于音乐片段的 arousal 高/低标签）以提升分类性能。
- **算法流程**（文字说明）：
  1. 采集128导EEG数据；2. 去除伪影并按情感标签分段；3. 计算每个2秒段在指定电极和频带上的平均功率；4. 构建24维特征向量；5. 划分训练/测试集；6. 训练SVM/RF/GB模型并调参（交叉验证）；7. 在测试集上评估准确率、宏F1、Cohen's kappa；8. 分析特征重要性，并测试加入额外唤醒特征后的性能变化。

## 3. 实验设计

- **数据集**：
  - 单受试者：一名专业音乐会钢琴家。
  - 刺激材料：来自巴赫、贝多芬、肖邦的**六类情感片段**（根据效价、节奏、能量/唤醒度、调性结构预先分类并经感知验证）。
  - 样本数：180个2秒无伪影片段，每类30个。
- **基准 (benchmark)**：理论随机水平，六类分类随机准确率为 **0.167**（1/6）。
- **对比方法**：
  - **分类器对比**：线性SVM vs 随机森林 vs 梯度提升。
  - **特征对比**：仅EEG频带特征 vs 加入二元唤醒特征后的EEG分类。

## 4. 资源与算力

- **文中未明确说明**所用的GPU型号、数量、训练时长等算力信息。
- **推测**：由于单被试、特征维度低（24维）、样本量小（180个），计算资源需求很低，使用普通CPU即可在数分钟内完成scikit-learn训练。论文未提及任何加速硬件。

## 5. 实验数量与充分性

- **实验组数**：主要进行了三类模型（SVM/RF/GB）的EEG-only分类实验，以及RF在添加唤醒特征后的二次实验。未进行消融实验（如逐频带、逐电极区域分析）或不同参数设置的大规模对比。
- **充分性与公平性**：
  - **优点**：使用了5折交叉验证和标准分类评估指标（准确率、宏F1、kappa），训练/测试分割明确。
  - **不足**：
    - **样本量极小**（每类30个片段），容易导致过拟合和统计方差大，模型泛化能力存疑。
    - **单受试者设计**，无法推广到其他演奏者，缺乏跨个体验证。
    - 未设置被动聆听对照组，无法直接对比主动与被动的情感解码差异。
    - 未控制运动伪迹的潜在混淆（不同情感演奏时动作幅度可能不同）。
    - 未报告置信区间或重复试验（如多次随机分割的结果稳定性）。
  - 总体而言，实验在方法学上合理但**充分性不足**，只能作为初步探索。

## 6. 论文的主要结论与发现

- **EEG-only分类**：所有模型均高于随机水平（0.167），随机森林性能最优：准确率0.42、宏F1=0.414、Cohen's kappa=0.30。
- **特征重要性**：θ、α、高β振荡在顶叶和枕叶区呈分布式贡献，**没有单一占主导的神经标记**，表明情感状态依赖多频段、多区域协同活动。
- **加入唤醒特征**：二元arousal标签显著提升随机森林准确率至0.58（宏F1=0.579, kappa=0.50），说明**唤醒维度在类别分离中起关键作用**。
- **核心发现**：主动表达性演奏过程中，EEG振荡包含可测量的情感状态统计结构，支持将情感研究从被动感知扩展到真实表演生态情境。

## 7. 优点

- **生态效度高**：采用专业钢琴家在自然演奏条件下的EEG，而非实验室静听任务，开创性地探索了运动-情感耦合的神经电生理特征。
- **方法创新**：将机器学习解码技术用于主动音乐表达，证明了单试次/短时间窗EEG可用于多类情感识别，拓展了情感计算的应用边界。
- **多分类器对比**：同时评估线性SVM、随机森林和梯度提升，选择了最优模型RF并提供了特征重要性分析，增强了结果可信度。
- **引入唤醒特征**：论证了情感维度（arousal）对分类的促进作用，有助于理解情感空间的组织。

## 8. 不足与局限

- **样本与泛化性**：单被试、每类仅30个样本，结论无法推广至其他演奏者或非专家音乐家，存在严重的**个体偏差风险**。
- **缺乏统计推断**：仅报告点估计，未提供置信区间、排列检验或重复实验，难以评估结果稳定性和过拟合程度。
- **混淆变量未控制**：不同情感音乐片段在速度、力度、指法等方面存在差异，可能引入运动相关伪迹或非情感差异，EEG差异未必纯粹源于“情感状态”。
- **频带选择局限**：仅选用了θ/α/高β三个频段，未考虑δ、低频β（13-20 Hz）或gamma频带，可能遗漏重要信息。
- **无被动聆听对照**：无法确定主动表演特有的神经活动特征是否类似被动感知或属于运动特有模式。
- **类别数量有限**：六类情感不足以覆盖情感空间的全貌，且未说明类别平衡性（文中似乎平衡）。
- **缺乏跨领域验证**：仅用EEG特征，未结合行为数据（如演奏录音的声学特征）进行多模态验证。

（完）
