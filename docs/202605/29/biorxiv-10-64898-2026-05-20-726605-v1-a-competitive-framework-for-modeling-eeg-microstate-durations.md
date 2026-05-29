---
title: A Competitive Framework for Modeling EEG Microstate Durations
title_zh: 用于建模脑电微状态持续时间的竞争框架
authors: "GOMEZ, C. M., Angulo Ruiz, B. Y."
date: 2026-05-22
pdf: "https://www.biorxiv.org/content/10.64898/2026.05.20.726605v1.full.pdf"
tags: ["query:eeg-ode-ln"]
score: 8.0
evidence: 用竞争框架建模EEG微状态时长
tldr: 脑电微状态的时间动态建模对理解神经活动至关重要。本研究提出竞争模型（C-model），利用几何分布描述微状态持续时间的右尾长尾，并通过引入难治期解释左尾短时动态。模型在60个会话中均能良好拟合分布，其中三分之一的会话显示微状态序列依赖。该框架为构建更全面的神经动力学模型奠定了基础。
source: biorxiv
selection_source: fresh_fetch
motivation: 现有模型难以同时捕捉微状态持续时间的短时稳定性和长尾分布，需要新的竞争性框架。
method: 提出C-model，采用几何分布表示微状态竞争失败概率，并引入难治期暂时增加当前网络稳定性，减少短时切换。
result: 模型拟合了所有60个会话的微状态持续时间分布，部分会话显示微状态序列依赖。
conclusion: C-model有效捕捉微状态时间结构的关键特征，可作为理解神经和行为动态的构建模块。
---

## 摘要
背景本研究考察了一种基于竞争的模型（C模型），旨在捕捉睁眼条件下从脑电图（EEG）记录中获得的连续脑微状态的时间动态。分析数据来自一个公开数据集，包含单个受试者60次实验的微状态序列[1]。当应用于微状态动态时，C模型假设在表达单个微状态的神经回路之间存在随机竞争。

方法该模型在概念层面（Marr框架中的计算层面）进行构建，并采用几何分布来解释微状态持续时间分布的长右尾，将其解释为当前活跃微状态持续“失败”的概率。为了解释短暂的左尾，模型纳入了当前活跃网络稳定性的短暂增加，或等效地，竞争微状态激活概率的暂时降低（不应期）。

结果该模型对所有60次实验的微状态持续时间分布均拟合良好。三分之一的实验在微状态身份上表现出与前一个微状态的顺序依赖性。

讨论这些结果表明，C模型捕捉了微状态时间结构的关键方面。此外，由于微状态概率可受到心理生理条件（包括先前活跃网络的影响）的调节，该模型可能作为更全面的神经生物学框架的构建模块，用于解释神经和行为动态。在这样的框架中，微状态序列可能源于支持微状态表达的神经网络之间的结构化竞争和流动。

## Abstract
BackgroundThis study examines a competition-based model (C-model) designed to capture the temporal dynamics of successive brain microstates derived from electroencephalography (EEG) recordings during eyes-open conditions. The analyzed data were obtained from a public repository comprising microstate sequences from 60 sessions of a single subject [1]. When applied to microstate dynamics, the C-model posits a stochastic competition among neural circuits underlying the expression of individual microstates.

MethodsThe model is formulated at a conceptual level (computational level in Marrs framework) and employs a geometric distribution to account for the long right tail of microstate duration distributions, interpreted as the probability of "failure" of the currently active microstate to persist. To account for the short-lived left tail, the model incorporates a transient increase in the stability of the currently active network, or equivalently, a temporary decrease in the activation probability of competing microstates (refractory period).

ResultsThe model provides a good fit to the microstate duration distributions across all 60 sessions. One third of sessions showed microstate identity sequential dependency with respect to the previous microstates.

DiscussionThese results suggest that the C-model captures key aspects of microstate temporal structure. Moreover, because microstate probabilities can be modulated by psychophysiological conditions--including the influence of previously active networks--the model may serve as a building block for more comprehensive neurobiological frameworks of neural and behavioral dynamics. In such frameworks, microstate sequences could emerge from structured competition and flow among neural networks supporting microstate expression.