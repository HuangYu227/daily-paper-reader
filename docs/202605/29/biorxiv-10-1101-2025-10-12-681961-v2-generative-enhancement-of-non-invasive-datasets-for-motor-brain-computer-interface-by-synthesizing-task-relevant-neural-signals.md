---
title: Generative enhancement of non-invasive datasets for motor brain-computer interface by synthesizing task-relevant neural signals
title_zh: 通过合成任务相关神经信号对运动脑机接口的非侵入数据集进行生成式增强
authors: "Kim, H., Kim, J. S."
date: 2026-05-24
pdf: "https://www.biorxiv.org/content/10.1101/2025.10.12.681961v2.full.pdf"
tags: ["query:tsc"]
score: 8.0
evidence: 基于GAN的神经信号时间序列合成用于数据增强
tldr: "运动脑机接口因任务相关神经特征数据有限，导致深度神经网络解码连续运动困难。本文提出生成对抗网络框架，从功能相关皮层合成M1信号以增强训练集。在目标导向臂伸任务中，增强后解码性能提升约10%，且无需真实M1信号即可维持。该方法在运动想象数据集上也提升了分类准确率，展示了信号生成网络增强脑机接口实现自由运动意图的潜力。"
source: biorxiv
selection_source: fresh_fetch
motivation: 运动脑机接口中，深度神经网络因单个数据集任务特征不足，难以解码高自由度连续运动。
method: 提出GAN框架，从功能相关皮层区域合成M1神经信号波形，增强个体数据集。
result: "MEG数据增强后解码精度提升约10%（p<0.05）；无真实M1时仍有效；运动想象数据集分类准确率提高。"
conclusion: 信号生成网络可有效增强运动BCI数据，促进实现自由意图运动解码。
---

## 摘要
尽管深度神经网络（DNN）在脑机接口（BCI）中的应用日益广泛，但开发能够解码连续运动（如肢体运动学）的高自由度系统仍然是一个重大挑战。这一困难源于个体神经信号数据集中任务特定神经特征的有限可用性。为了克服这一问题，我们提出了一个生成对抗网络（GAN）框架，以丰富神经信号数据集中的训练特征。具体而言，我们从功能相关的皮层区域合成了初级运动皮层（M1）的人工神经信号波形，从而增强神经数据集，以便通过DNN改进运动学解码。使用目标导向手臂伸展任务期间的脑磁图（MEG）记录，我们的结果表明，用GAN合成的M1信号增强个体数据集显著提高了解码性能约10%（p < 0.05）。即使在没有真实M1信号的情况下，这种改进的性能也能持续。我们进一步将所提出的增强方法推广到运动想象BCI竞赛数据集，以提高分类准确率。我们的结果突出了信号生成网络在改进和增强运动BCI以实现自由意图运动方面的潜力。

## Abstract
Despite the increasing adoption of deep neural networks (DNNs) in brain-computer interfaces (BCIs), developing high-degree-of-freedom (DOF) systems capable of decoding continuous movements, such as limb kinematics, remains a significant challenge. This difficulty stems from limited availability of task-specific neural features within individual neural signal datasets. To overcome this, we proposed a generative adversarial network (GAN) framework to enrich training features within neural signal datasets. Specifically, we synthesized artificial neural signal waveforms of the primary motor cortex (M1) from functionally related cortical regions, thereby enhancing neural datasets for improved motor kinematics decoding via DNN. Using magnetoencephalography (MEG) recordings during goal-directed arm-reaching tasks, our results showed that enhancing individual datasets with GAN-synthesized M1 signals significantly improved decoding performance by about 10% (p < 0.05). Such improved performance is sustained even in the absence of real M1 signals. We further generalized the proposed enhancement to the motor imagery BCI competition dataset to improve classification accuracy. Our results highlight the potential of signal-generative networks to improve and augment motor BCIs to achieve freely intended movements.