---
title: "Directed neural interactions in fMRI: a comparison between Granger Causality and Effective Connectivity"
title_zh: fMRI中的定向神经交互：格兰杰因果与有效连接性的比较
authors: "Allegra, M., Gilson, M., Brovelli, A."
date: 2026-04-29
pdf: "https://www.biorxiv.org/content/10.1101/2024.02.22.581068v3.full.pdf"
tags: ["query:tsc"]
score: 8.0
evidence: 比较Granger因果和有效连接，用于神经时间序列的时序因果发现
tldr: 网络神经科学需推断脑区方向性交互，fMRI常用Granger因果（GC）和有效连接（EC）。通过连续与离散时间随机过程映射，推导出EC与经噪声方差校正后的GC间存在近似二次关系。模拟表明该关系仅在大量数据时显现，并在HCP大尺度fMRI数据中得到验证。研究为两种方法在脑网络重建中的应用提供指导，阐明共性与偏差。
source: biorxiv
selection_source: fresh_fetch
motivation: 比较Granger因果分析和有效连接两种fMRI方向性交互推断方法，揭示其数学联系与差异。
method: 基于MOU和MVAR过程映射，解析推导EC与经噪声方差校正后的GC之间的近似二次关系。
result: 模拟验证了理论关系，但需大量数据才在有限时间序列中显现；HCP数据证实了组水平上的关系。
conclusion: 为GC和EC在脑网络重建中的使用提供方法学指导，明确两者的共性与特定偏差。
---

## 摘要
网络神经科学的一个关键挑战是理解大脑区域之间的相互作用及其如何在认知过程中促进信息的编码和广播。这需要通过计算工具从神经时间序列中推断大脑区域之间的定向关系。对于fMRI，最常见的方法基于格兰杰因果（GC）分析和有效连接（EC）模型。尽管概念框架不同，但fMRI的GC和EC模型基于相似的数学假设，以连续时间和离散时间线性随机模型为基础。基于多变量Ornstein-Uhlenbeck（MOU）与多变量自回归（MVAR）过程之间的映射，我们通过重新缩放GC以补偿源和目标的不相等噪声方差，分析性地得到了EC与GC之间的近似二次关系。模拟表明，只有在大量数据可用时，这些关系才能在有限时间序列中观察到，这意味着在真实fMRI实验中，它们可能仅在组水平上出现。我们通过在人类连接组项目的大规模fMRI数据集中系统比较EC和GC来验证这一预测。总体而言，我们的发现通过清晰阐明两种方法之间的共同点及其各自的特异性和偏差，可以为GC和EC在大脑网络重建中的使用提供方法论和解释性指导。

## Abstract
A key challenge for network neuroscience is to understand the role of interactions between brain regions and how they contribute to the encoding and broadcasting of information within cognitive processes. This requires computational tools to infer directional relations between brain regions from neural time series. For fMRI, the most common approaches are based on Granger causality (GC) analysis and effective connectivity (EC) models. Despite their different conceptual framing, GC and EC models for fMRI are based on similar mathematical assumptions, grounded on continuous- and discrete-time linear stochastic models. Based on a mapping between multivariate Ornstein-Uhlenbeck (MOU) and multivariate autoregressive (MVAR) processes, we analytically obtain an approximately quadratic relation between EC and GC, after rescaling the GC to compensate for unequal noise variances of the source and target. Simulations show that these relations can be observed in finite time series only if a large amount of data is available, implying that they may emerge only at a group level in real fMRI experiments. We verified this prediction by systematically comparing EC and GC in a large-scale fMRI data set from the Human Connectome Project. Overall, our findings can provide methodological and interpretational guidance in the usage of GC and EC for brain network reconstruction by clearly elucidating what is common between the two methods, but also their respective specificities and biases.