---
title: "The cost of data aggregation: spatiotemporal compression obscures causal attribution in biodiversity monitoring"
title_zh: 数据聚合的代价：时空压缩模糊了生物多样性监测中的因果归因
authors: "Malinowska, K., Wawrzynowicz, M., Markowska, K., Chodkiewicz, T., Butler, S., Kuczynski, L."
date: 2026-06-04
pdf: "https://www.biorxiv.org/content/10.1101/2025.05.17.654658v5.full.pdf"
tags: ["query:tsc"]
score: 7.0
evidence: 时间序列聚合对因果归因的影响
tldr: 生态监测常通过时空聚合简化高维数据，但可能破坏协方差结构，掩盖种群变化的真正驱动因素。本研究利用虚拟物种模拟和虚拟生态学家方法，对比了空间聚合（常规时间序列TS）、时间聚合（静态物种分布模型SDM）与全分辨率时空（FRST）框架的因果归因准确性。结果表明：空间聚合导致因果推断完全失效（敏感度0.00），时间聚合稍好（准确率0.68），而FRST框架表现最优（准确率0.88、敏感度0.84、特异性0.93）。此外，变量选择存在悖论：双重惩罚收缩略微改善TS，但降低了SDM和FRST的特性。研究揭示了数据聚合的信息损失代价，强调采用全分辨率、机械信息框架对生物多样性监测和因果归因至关重要。
source: biorxiv
selection_source: fresh_fetch
motivation: 数据聚合（时空压缩）可能破坏协方差结构，导致因果归因不准确，当前生态监测分析方法存在根本性缺陷。
method: 通过虚拟物种模拟生成带已知因果驱动的时空数据集，并模拟20年大规模鸟类监测，比较TS、SDM和FRST框架的归因性能。
result: 空间压缩（TS）完全无法识别真实驱动（准确率0.50，敏感度0.00）；时间压缩（SDM）准确率0.68；全分辨率FRST准确率0.88、敏感度0.84、特异性0.93。
conclusion: 数据聚合降低信息价值，全分辨率、机械信息框架是可靠因果归因和生物多样性监测的关键。
---

## 摘要
保护决策需要准确识别种群变化的原因。生态学家通常依赖聚合高维监测数据的分析流程。我们假设，数据压缩——无论是空间上的（如传统时间序列分析）还是时间上的（如静态物种分布模型）——会破坏协方差结构，模糊因果驱动因素的识别。为了量化这种“聚合代价”，我们使用虚拟物种进行了严格的模拟实验，以建立种群驱动因素的已知“真实情况”。然后，我们采用虚拟生态学家方法模拟了为期20年的大规模鸟类监测计划，生成了真实的时空数据集来评估分析流程。我们将聚合时间序列和静态物种分布模型方案的因果归因准确性与全分辨率时空框架进行了基准比较，后者保留了原始数据维度并整合了机制性的时空协方差结构。模拟结果显示，空间压缩严重损害了因果推断：未受惩罚的时间序列模型未能检测到任何真正的潜在驱动因素（准确率=0.50，灵敏度=0.00）。时间压缩（静态物种分布模型）表现稍好（准确率=0.68），而全分辨率时空模型实现了更优的准确率（0.88）、灵敏度（0.84）和特异性（0.93）。此外，我们发现了变量选择悖论：双重惩罚收缩略微改善了低效的时间序列模型，但通过迫使虚假的相关变量吸收残差方差，降低了静态物种分布模型和全分辨率时空框架的特异性。我们的研究结果表明，涉及数据聚合的方案降低了大规模监测数据集的信息价值。全分辨率、基于机制信息的框架对于可靠的因果归因和稳健的生物多样性监测至关重要。

## Abstract
Conservation decision-making requires accurate identification of causes of population changes. Ecologists often rely on analytical protocols that aggregate high-dimensional monitoring data. We hypothesise that compressing data - either spatially, as in conventional time series (TS) analysis, or temporally, as in static species distribution models (SDMs) - destroys covariance structures and obscures the identification of causal drivers. To quantify this "aggregation cost", we conducted a rigorous simulation experiment using virtual species to establish a known "ground truth" of population drivers. We then employed a virtual ecologist approach to mimic a 20-year large-scale bird monitoring scheme, and generate realistic spatiotemporal datasets to evaluate the analytical pipelines. We benchmarked the causal attribution accuracy of aggregated TS and SDM protocols against a full-resolution spatiotemporal (FRST) framework, which retains native data dimensions and integrates mechanistic spatiotemporal covariance structures. Our simulations revealed that spatial compression severely compromises causal inference: unpenalised TS models failed to detect any true underlying drivers (accuracy = 0.50, sensitivity = 0.00). Temporal compression (SDMs) performer moderately better (accuracy = 0.68), while the FRST model achieved superior accuracy (0.88), sensitivity (0.84), and specificity (0.93). Furthermore, we identified a variable selection paradox: double penalty shrinkage marginally improved underpowered TS models, although it degraded the specificity of SDM and FRST frameworks by forcing spurious, correlated variables to absorb residual variance. Our findings demonstrate that protocols that involve data aggregation reduce the informational value of large-scale monitoring datasets. Full-resolution, mechanistically informed frameworks are essential for reliable causal attribution and robust biodiversity monitoring.