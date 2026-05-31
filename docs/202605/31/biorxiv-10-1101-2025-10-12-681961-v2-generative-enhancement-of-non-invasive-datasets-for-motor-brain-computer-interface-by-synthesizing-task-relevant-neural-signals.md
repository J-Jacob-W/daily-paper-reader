---
title: Generative enhancement of non-invasive datasets for motor brain-computer interface by synthesizing task-relevant neural signals
title_zh: 通过合成任务相关神经信号对运动脑机接口的非侵入式数据集进行生成式增强
authors: "Kim, H., Kim, J. S."
date: 2026-05-24
pdf: "https://www.biorxiv.org/content/10.1101/2025.10.12.681961v2.full.pdf"
tags: ["query:eeg-ode-ln"]
score: 6.0
evidence: 基于GAN的数据增强用于运动脑机接口，增强脑电图解码
tldr: "运动脑机接口的连续解码受限于神经信号数据不足。本文提出用生成对抗网络从功能相关皮层区域合成M1信号波形，增强个体数据集。在MEG手臂到达任务中，增强后解码性能提升约10%，即便没有真实M1信号也能保持。该方法也推广到运动想象竞赛数据集，提高了分类准确率。"
source: biorxiv
selection_source: fresh_fetch
motivation: 运动脑机接口解码连续运动需大量任务相关神经特征，但个体数据集有限，制约深度学习应用。
method: 提出生成对抗网络框架，从功能相关皮层区域合成M1神经信号波形，扩充训练数据集。
result: "在MEG手臂到达任务中，增强个体数据集使运动解码性能提升约10%（p<0.05），并在无真实M1信号时保持提升。"
conclusion: 信号生成网络可有效增强运动脑机接口数据集，促进实现自由意图的运动解码。
---

## 摘要
尽管深度神经网络(DNNs)在脑机接口(BCI)中的应用日益增多，但开发能够解码连续运动(如肢体运动学)的高自由度(DOF)系统仍然是一个重大挑战。这一困难源于单个神经信号数据集中任务特定神经特征的有限可用性。为了克服这一问题，我们提出了一种生成对抗网络(GAN)框架来丰富神经信号数据集中的训练特征。具体来说，我们从功能相关的皮层区域合成初级运动皮层(M1)的人工神经信号波形，从而增强神经数据集，以通过DNN改进运动学解码。使用目标导向的手臂伸展任务中的脑磁图(MEG)记录，我们的结果表明，用GAN合成的M1信号增强单个数据集，显著提高了解码性能约10%(p < 0.05)。即使在没有真实M1信号的情况下，这种改进的性能也能持续。我们进一步将所提出的增强方法推广到运动想象BCI竞赛数据集上，以提高分类精度。我们的结果凸显了信号生成网络在改善和增强运动BCI以实现自由意向运动方面的潜力。

## Abstract
Despite the increasing adoption of deep neural networks (DNNs) in brain-computer interfaces (BCIs), developing high-degree-of-freedom (DOF) systems capable of decoding continuous movements, such as limb kinematics, remains a significant challenge. This difficulty stems from limited availability of task-specific neural features within individual neural signal datasets. To overcome this, we proposed a generative adversarial network (GAN) framework to enrich training features within neural signal datasets. Specifically, we synthesized artificial neural signal waveforms of the primary motor cortex (M1) from functionally related cortical regions, thereby enhancing neural datasets for improved motor kinematics decoding via DNN. Using magnetoencephalography (MEG) recordings during goal-directed arm-reaching tasks, our results showed that enhancing individual datasets with GAN-synthesized M1 signals significantly improved decoding performance by about 10% (p < 0.05). Such improved performance is sustained even in the absence of real M1 signals. We further generalized the proposed enhancement to the motor imagery BCI competition dataset to improve classification accuracy. Our results highlight the potential of signal-generative networks to improve and augment motor BCIs to achieve freely intended movements.