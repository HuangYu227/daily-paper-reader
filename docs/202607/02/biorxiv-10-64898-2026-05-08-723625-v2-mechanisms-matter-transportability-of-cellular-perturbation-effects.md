---
title: "Mechanisms Matter: Transportability of Cellular Perturbation Effects"
title_zh: 机制至关重要：细胞扰动效应的可迁移性
authors: "Qi, S.-a., Chapfuwa, P."
date: 2026-07-02
pdf: "https://www.biorxiv.org/content/10.64898/2026.05.08.723625v2.full.pdf"
tags: ["query:tsc"]
score: 7.0
evidence: 因果可迁移性与细胞扰动因果模拟器
tldr: 预测细胞扰动响应在跨上下文泛化中面临挑战，深度学习模型性能常不及简单基线。基于因果可转移性理论，本文指出泛化由共享因果机制决定，而非分布相似性。通过构建因果模拟器生成半合成数据，并引入Vendi多样性分数诊断模式崩溃，实验揭示跨上下文泛化存在显著差距，模型无法泛化至不同因果机制的上下文。工作强调需要机制性归纳偏差和多样性感知评估。
source: biorxiv
selection_source: fresh_fetch
motivation: 现有模型在跨上下文细胞扰动预测中未见显著提升，因缺乏对因果机制泛化规律的理解。
method: 利用因果可转移性理论，开发因果模拟器生成半合成Perturb-seq数据，并引入Vendi分数评估模式崩溃。
result: 实验表明跨上下文性能大幅下降至基线水平，无模型能泛化至不同因果机制的上下文。
conclusion: 需引入跨上下文评估、多样性指标及机制驱动的归纳偏差以提升泛化。
---

## 摘要
预测跨生物背景下细胞对遗传或化学扰动的响应是药物开发和疾病理解的核心。尽管数据和模型规模不断增加，深度学习模型并未始终优于简单基线。利用因果可迁移性理论，我们展示了跨上下文泛化由共享因果机制主导，而不仅仅是分布相似性。为了实现受控评估，我们开发了一个因果模拟器，生成具有可调节机制差异的真实半合成Perturb-seq数据集，并提供具有已知真实因果结构的基准。此外，我们将Vendi多样性分数适应于扰动场景，作为模式崩溃的诊断指标——标准每扰动指标无法察觉的失败模式。在四个深度学习模型和六个简单基线上，对半合成和真实Perturb-seq数据集进行的大量实验揭示了跨上下文泛化差距：跨上下文分割下的性能显著下降，通常降至简单基线水平。值得注意的是，即使在完全指定因果结构的合成数据上，也没有模型能够跨不同因果机制的上下文进行泛化。这些结果强调了跨上下文评估、多样性感知指标以及基于机制的归纳偏置的必要性。

## Abstract
Predicting cellular responses to genetic or chemical perturbations across biological contexts is central to drug development and disease understanding. Despite increases in data and model scale, deep learning models have not consistently outperformed simple baselines. Leveraging causal transportability theory, we show that cross-context generalization is governed by shared causal mechanisms, not merely distributional similarity. To enable controlled evaluation, we develop a causal simulator that generates realistic semi-synthetic Perturb-seq datasets with tunable mechanistic divergence, providing benchmarks with known ground-truth causal structure. Further, we adapt the Vendi diversity score to the perturbation setting as a diagnostic for mode collapse, a failure mode invisible to standard per-perturbation metrics. Extensive experiments across four deep learning models and six simple baselines on semi-synthetic and real Perturb-seq datasets reveal a cross-context generalization gap: performance under cross-context splits drops substantially, often to simple baseline levels. Notably, even on synthetic data with fully specified causal structure, no model generalized across contexts with different causal mechanisms. These results underscore the need for cross-context evaluation, diversity-aware metrics, and mechanistically grounded inductive biases.