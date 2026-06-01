---
title: Generative enhancement of non-invasive datasets for motor brain-computer interface by synthesizing task-relevant neural signals
title_zh: 通过合成任务相关神经信号对运动脑机接口的非侵入式数据集进行生成式增强
authors: "Kim, H., Kim, J. S."
date: 2026-05-24
pdf: "https://www.biorxiv.org/content/10.1101/2025.10.12.681961v2.full.pdf"
tags: ["query:eeg-ode-ln"]
score: 6.0
evidence: 生成式数据增强用于脑机接口；可迁移至情绪识别
tldr: "针对脑机接口中解码连续运动所需任务相关神经特征有限的问题，提出生成对抗网络框架合成初级运动皮层信号增强数据集。在脑磁图手臂伸展任务中，增强后解码性能提升约10%，且无真实信号时仍有效。进一步在运动想象数据集上验证了分类准确率提升。该方法有望推动自由意图运动脑机接口发展。"
source: biorxiv
selection_source: fresh_fetch
motivation: 个体神经信号数据集中任务特定特征有限，限制了高自由度运动解码性能。
method: 用生成对抗网络从功能相关皮层区域合成初级运动皮层（M1）神经信号波形，扩充训练数据。
result: "增强个体数据集后运动解码性能提升约10%（p<0.05），且无真实M1信号时改进仍持续。"
conclusion: 信号生成网络能有效增强运动脑机接口数据集，提升解码精度，促进自由意图运动实现。
---

## 摘要
尽管深度神经网络（DNN）在脑机接口（BCI）中的应用日益广泛，开发能够解码连续运动（如肢体运动学）的高自由度（DOF）系统仍然是一个重大挑战。这一困难源于单个神经信号数据集中任务特定神经特征的有限可用性。为了克服这一问题，我们提出了一种生成对抗网络（GAN）框架来丰富神经信号数据集中的训练特征。具体来说，我们从功能相关的皮层区域合成了初级运动皮层（M1）的人工神经信号波形，从而增强神经数据集，以通过DNN改善运动学解码性能。利用目标导向的手臂伸展任务中的脑磁图（MEG）记录，我们的结果显示，使用GAN合成的M1信号增强单个数据集可显著提高解码性能约10%（p < 0.05）。即使在缺少真实M1信号的情况下，这种改进的性能也能保持。我们进一步将所提出的增强方法推广到运动想象BCI竞赛数据集，以提高分类准确率。我们的结果突出了信号生成网络在改进和增强运动BCI以实现自由意向运动方面的潜力。

## Abstract
Despite the increasing adoption of deep neural networks (DNNs) in brain-computer interfaces (BCIs), developing high-degree-of-freedom (DOF) systems capable of decoding continuous movements, such as limb kinematics, remains a significant challenge. This difficulty stems from limited availability of task-specific neural features within individual neural signal datasets. To overcome this, we proposed a generative adversarial network (GAN) framework to enrich training features within neural signal datasets. Specifically, we synthesized artificial neural signal waveforms of the primary motor cortex (M1) from functionally related cortical regions, thereby enhancing neural datasets for improved motor kinematics decoding via DNN. Using magnetoencephalography (MEG) recordings during goal-directed arm-reaching tasks, our results showed that enhancing individual datasets with GAN-synthesized M1 signals significantly improved decoding performance by about 10% (p < 0.05). Such improved performance is sustained even in the absence of real M1 signals. We further generalized the proposed enhancement to the motor imagery BCI competition dataset to improve classification accuracy. Our results highlight the potential of signal-generative networks to improve and augment motor BCIs to achieve freely intended movements.