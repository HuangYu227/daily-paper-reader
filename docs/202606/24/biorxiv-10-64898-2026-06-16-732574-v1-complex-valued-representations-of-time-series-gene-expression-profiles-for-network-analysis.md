---
title: Complex-valued representations of time-series gene expression profiles for network analysis
title_zh: 用于网络分析的时间序列基因表达谱的复值表示
authors: "Sun, J., Cao, W., Ikumi, K., Shimizu, K. K., Sese, J."
date: 2026-06-22
pdf: "https://www.biorxiv.org/content/10.64898/2026.06.16.732574v1.full.pdf"
tags: ["query:fe"]
score: 6.0
evidence: 时间序列基因表达的复值特征提取
tldr: 时间序列基因表达分析常用实值向量和相关性度量，但难以捕捉时序动态。受量子信息理论启发，本研究提出将表达谱编码为复值向量，用振幅表示表达水平、相位表示时间差异，并通过保真度量化基因相似性。在多个物种数据集上，该方法构建的网络社区与加权相关网络分析和模糊C均值聚类结果相当。此外，量子计算模拟表明保真度估计精度低且成本高，表明该方法目前是对常规技术的补充而非替代。
source: biorxiv
selection_source: fresh_fetch
motivation: 传统实值向量表示无法充分利用时间序列中的相位信息，受量子信息启发，探索复值编码以捕捉动态基因调控。
method: 将基因表达谱编码为复值向量，振幅对应表达水平，相位编码时间差或局部变化方向，利用保真度度量基因间相似性并构建网络。
result: 不同编码模型产生与相关性分布不同但相关的保真度分布；检测到的社区捕获主要时序表达程序，功能富集与常规方法可比。
conclusion: 该框架提供了一种时间转录组的互补分析视角，但目前并非优于经典方法的统一替代方案。
---

## 摘要
时间序列RNA测序为研究动态基因调控提供了强大的框架，然而传统分析通常将基因表达谱表示为欧几里得空间中的实值向量，并使用相关性或距离来量化相似性。受量子信息理论启发，我们提出了一种框架，将时间序列基因表达谱编码为希尔伯特空间中包含幅度和相位分量的复值向量。我们设计了多种编码模型，将基因表达表示为复值向量的幅度，将时间差异编码在相位中，并扩展相位表示以包含局部表达变化的方向。然后使用保真度量化基因-基因相似性，保真度衡量两个编码向量之间的重叠。使用跨不同物种和生物学背景的时间序列RNA-seq数据集进行评估表明，不同的编码模型产生了不同的保真度分布，这些分布与传统的相关性度量相关但又有所区别。然后，我们使用成对保真度值构建基因-基因网络，并检测包含具有相似时间谱的基因的群落。尽管不同编码模型的保真度分布存在差异，但所得群落捕获了主要的时间表达程序，基于基因本体论和京都基因与基因组百科全书通路分析的功能注释提供了探索性的生物学背景。检测到的群落与使用传统方法（包括加权相关网络分析和模糊C均值聚类）获得的结果相当。此外，作为概念验证，我们进行了SWAP测试电路模拟，以在量子计算机上模拟保真度计算；在噪声感知条件下，这些模拟产生的保真度估计准确性较低，计算成本高于经典计算。作为概念验证，本研究提供了时间转录组组织的互补视角，而非传统方法的统一优越替代方案。

## Abstract
Time-series RNA sequencing provides a powerful framework for studying dynamic gene regulation, yet conventional analyses usually represent gene expression profiles as real-valued vectors in Euclidean space and quantify similarity using correlation or distance. Inspired by quantum information theory, we present a framework for encoding time-series gene expression profiles as complex-valued vectors comprising amplitude and phase components in Hilbert space. We designed multiple encoding models to represent gene expression in the amplitude of complex-valued vectors, encode temporal differences in the phase, and extend the phase representation to incorporate the direction of local expression changes. Gene-gene similarity was then quantified using fidelity, which measures the overlap between two encoded vectors. Evaluation using time-series RNA-seq datasets across diverse species and biological contexts showed that different encoding models produced distinct fidelity distributions that were related to, but distinct from, conventional correlation measures. We then constructed gene-gene networks using pairwise fidelity values and detected communities containing genes with similar temporal profiles. Although fidelity distributions differed across encoding models, the resulting communities captured major temporal expression programs, and functional annotations based on gene ontology and Kyoto encyclopedia of genes and genomes pathway analyses provided exploratory biological context. The detected communities were comparable to those obtained using conventional methods, including weighted correlation network analysis and fuzzy c-means clustering. Furthermore, as a proof-of-concept, we performed SWAP-test circuit simulations to mimic fidelity computation on a quantum computer; under noise-aware conditions, these simulations produced less accurate fidelity estimates with higher computational cost than classical computation. As a proof-of-concept, this study provides a complementary view of temporal transcriptome organization, rather than a uniformly superior alternative to conventional methods.