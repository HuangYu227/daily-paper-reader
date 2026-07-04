---
title: Optical flow reveals motility signatures for inferring pathogenic bacterial mixture compositions via temporal convolutional networks
title_zh: 光流揭示运动特征：通过时间卷积网络推断病原菌混合组成
authors: "Fujita, Y., Nagase, Y., Pathak, S., Moro, A., Suzuki, H., Koiwai, K., Umeda, K."
date: 2026-06-29
pdf: "https://www.biorxiv.org/content/10.64898/2026.06.29.735172v1.full.pdf"
tags: ["query:fe"]
score: 6.0
evidence: 利用时间卷积网络从运动数据中提取时间序列特征
tldr: "水产养殖中病原菌的快速识别对疾病防控至关重要。现有方法依赖荧光标记或培养，无法实时分析混合菌群动态。本文从显微视频中提取24种运动特征，使用时序卷积网络（TCN）学习其时间结构，以分类哈维弧菌与环境菌的混合比例。该方法达到93.3%的准确率，优于传统方法。研究表明混合菌群的区分不取决于绝对运动速度，而取决于集体对齐及其时间稳定性。该工作为无标记自动筛选和机器人微生物学应用提供了计算框架。"
source: biorxiv
selection_source: fresh_fetch
motivation: 现有细菌混合比例评估依赖荧光标记或培养，难以实现实时、无标记的动态定量分析。
method: 从显微视频中提取24种可解释的运动描述符，并使用时序卷积网络（TCN）学习时间序列特征。
result: "在哈维弧菌与环境菌混合比例分类任务中达到93.3%准确率，优于静态统计和其他机器学习模型。"
conclusion: 混合菌群的区分关键在于群体对齐的时序稳定性而非绝对运动速度，为无标记自动筛选提供了新策略。
---

## 摘要
随着全球食品需求的快速增长，水产养殖已成为未来粮食安全的关键支柱。然而，水产养殖系统仍易受病原菌侵袭，快速识别拮抗微生物对于可持续疾病控制至关重要。传统评估方法依赖于荧光标记或培养后分析，限制了实时、无标记地量化混合微生物种群动态相互作用的能力。本文提出一种计算框架，利用从显微视频中提取的时间序列运动特征，对哈维氏弧菌与环境细菌的混合比例进行分类。我们定义了24个可解释的运动描述符，并采用时间卷积网络（TCN）学习其时序结构。该方法实现了93.3%的分类准确率，优于传统静态统计方法和替代机器学习模型。这些发现表明，微生物群落中的混合区分并非由绝对运动幅度决定，而是由集体排列及其时间稳定性所支配。本研究建立了一个时间分辨计算框架，用于量化混合微生物种群中的动态集体秩序，并凸显了其在无标记自动化筛选和机器人微生物学应用中的潜力。

作者总结：细菌感染对水产养殖构成重大威胁，快速识别拮抗微生物对于可持续疾病管理至关重要。现有筛选方法通常需要荧光标记或培养后分析，使得混合细菌种群的实时评估变得困难。本研究表明，从显微视频中提取的时间序列运动特征可准确分类哈维氏弧菌与环境细菌的混合比例。通过将TCN应用于24个可解释的运动描述符，我们在不依赖荧光标记的情况下实现了高分类准确率。分析表明，集体方向排列及其时间稳定性（而非绝对游动速度）是混合区分的关键决定因素。本研究引入了一种计算策略，用于量化微生物群落中的动态集体秩序，并支持开发用于微生物学应用的无标记自动化筛选平台。

## Abstract
With the rapid expansion of global food demand, aquaculture has become a critical pillar for future food security. However, aquaculture systems remain highly vulnerable to pathogenic bacteria, and rapid identification of antagonistic microbes is essential for sustainable disease control. Conventional evaluation approaches rely on fluorescence labeling or post-culture assays, limiting the ability to quantify dynamic interactions in mixed microbial populations in a real-time and label-free manner. Here, we propose a computational framework for classifying the mixing ratio of Vibrio harveyi and environmental bacteria using time-series motion features extracted from microscopy videos. We defined 24 interpretable motility descriptors and employed a Temporal Convolutional Network (TCN) to learn their temporal structure. The proposed method achieved a classification accuracy of 93.3%, outperforming conventional static statistical approaches and alternative machine learning models. These findings indicate that mixture discrimination in microbial communities is governed not by absolute motility magnitude, but by collective alignment and its temporal stability. Our study establishes a time-resolved computational framework for quantifying dynamic collective order in mixed microbial populations and highlights its potential for label-free automated screening and robotic microbiological applications.

Author summaryBacterial infections pose a major threat to aquaculture, and rapid identification of antagonistic microbes is essential for sustainable disease management. Existing screening approaches often require fluorescent labeling or post-culture analysis, making real-time evaluation of mixed bacterial populations difficult. In this study, we show that mixture ratios of Vibrio harveyi and environmental bacteria can be accurately classified from time-series motion features extracted from microscopy videos. By applying TCN to 24 interpretable motility descriptors, we achieved high classification accuracy without relying on fluorescent markers. Our analysis demonstrates that collective directional alignment and its temporal stability, rather than absolute swimming speed, are the key determinants of mixture discrimination. This work introduces a computational strategy for quantifying dynamic collective order in microbial communities and supports the development of label-free, automated screening platforms for microbiological applications.