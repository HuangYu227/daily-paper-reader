---
title: Unsupervised Representation Learning Reveals Individualized Neurophysiological Profiles
title_zh: 无监督表示学习揭示个体化神经生理特征
authors: "Lapatrie, M., da Silva Castanheira, J., Aydin, I., Baillet, S."
date: 2026-06-26
pdf: "https://www.biorxiv.org/content/10.64898/2026.02.10.705127v2.full.pdf"
tags: ["query:fe"]
score: 6.0
evidence: 从静息态脑磁图时间序列中无监督学习表示
tldr: "人类脑活动存在稳定的个体特异性特征，形成神经生理特征。现有方法依赖参与者标签或监督目标，难以区分稳定生物学与可利用特性。本文提出参与者不可知自动编码器框架，仅以重建为目标，从短时静息态MEG数据中学习潜在空间，无需标签即可提取判别性特征。结果表明，session内120秒数据识别准确率达93.3%，短至14秒即超越传统基线；session间准确率49.5%；年龄预测R²=0.318。该工作建立了可扩展且可解释的参与者不可知表示学习方法。"
source: biorxiv
selection_source: fresh_fetch
motivation: 现有模型依赖标签或监督目标，难以区分稳定生物学与可探测的个体特性。
method: 提出参与者不可知自动编码器，仅以重建为目标从短时静息态MEG段学习潜在空间。
result: "session内120秒准确率93.3%，14秒即超基线；session间49.5%；年龄预测R²=0.318。"
conclusion: 参与者不可知表示学习为神经生理特征提取提供了可扩展且可解释的方案。
---

## 摘要
人类大脑活动包含稳定、个体特有的特征，这些特征可持续数月至数年，形成神经生理特征。大多数基于模型的特征提取方法使用参与者标签或有监督目标，这使得难以判断成功的区分是否反映了稳定的生物学特性还是可被利用的特异性。我们引入了一种参与者无关的自编码器框架，该框架以重建作为唯一训练目标，从短暂的静息态脑磁图（MEG）片段中提取特征。在没有参与者标签的情况下，从学习到的潜在空间中出现具有区分性的特征。在同一会话内，自编码器特征在120秒时达到93.3%的准确率，当参与者特异性解剖信息从源重建中剔除时，即使记录短至14秒，其性能也超过了功能连接、频谱和对比基线。在不同会话间，区分能力高于随机水平（预训练自编码器的会话间准确率为49.5%）。此外，这些特征对年龄的预测比基线更准确（r²=0.318），并且解码器实现了频谱和连接空间的基于扰动的敏感性分析。这确立了参与者无关的表示学习作为一种可扩展且可解释的特征提取方法。

## Abstract
Human brain activity contains stable, individual-specific features that persist over months to years, forming neurophysiological profiles. Most model-based profiling approaches use participant labels or supervised objectives, making it difficult to determine whether successful differentiation reflects stable biology or exploitable idiosyncrasies. We introduce a participant-agnostic autoencoder framework that derives profiles from brief resting-state magnetoencephalography (MEG) segments using reconstruction as sole training objective. Discriminative profiles emerged from the learned latent space without participant labels. Within-session, autoencoder profiles reached 93.3% accuracy at 120 s, exceeding functional-connectivity, spectral, and contrastive baselines with recordings as short as 14 s when participant-specific anatomy was withheld from source reconstruction. Differentiation generalized above chance across recording sessions (between-session accuracy 49.5% for the pretrained autoencoder). Profiles also predicted age more accurately than baselines (r2=0.318), and the decoder enabled perturbation-based sensitivity analyses in spectral and connectivity spaces. This establishes participant-agnostic representation learning as a scalable and interpretable profiling.