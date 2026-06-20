---
title: "SMS: Symmetric Mediation Statistics for Powerful High-Dimensional Mediation Analysis"
title_zh: SMS：用于强大高维中介分析的对称中介统计量
authors: "Wang, Y., Yan, S., Wang, H.-J., Hu, Y.-J."
date: 2026-06-15
pdf: "https://www.biorxiv.org/content/10.64898/2026.06.10.730748v1.full.pdf"
tags: ["query:tsc"]
score: 6.0
evidence: 高维中介分析方法用于因果推断，提出对称检验统计量
tldr: 高维中介分析中，测试复合零假设和保持功效面临挑战，尤其当暴露-中介与中介-结果关联强度不平衡时。SMS框架基于对称中介统计量，通过对称性整体校准复合零分布以控制FDR，并可灵活组合p值或直接使用效应量构建综合检验。模拟实验显示SMS在控制FDR的同时灵敏度提升约20个百分点，在代谢组学和DNA甲基化数据中发现多个已有方法遗漏的中介变量。SMS为高维中介分析提供了更强大且稳健的工具。
source: biorxiv
selection_source: fresh_fetch
motivation: 现有方法在测试复合零假设及处理关联强度不平衡时，FDR控制不佳且功效有限。
method: 提出SMS框架，基于对称中介统计量，利用对称性校准复合零分布，并支持灵活组合p值或效应量构建综合检验。
result: 模拟中SMS控制FDR并提升灵敏度约20个百分点，真实数据分析发现5个已有方法遗漏的中介。
conclusion: SMS有效控制FDR并增强检测能力，尤其适用于关联强度不平衡的高维中介分析。
---

## 摘要
背景
高维特征（尤其是分子组学特征）的中介分析为揭示人类健康和疾病背后的生物学机制提供了重要机会。然而，两个核心统计挑战依然存在：检验复合零假设，以及在暴露-中介和中介-结局关联的统计学显著性差异较大时保持检验功效。现有方法通常依赖于准确估计三种零假设类型的比例或两个关联p值的最大值，可能无法始终良好控制FDR，且在非均衡显著性下功效有限。

方法
我们提出SMS，一种基于对称中介统计量的新统计框架。通过利用对称性，SMS将复合零分布作为一个整体进行校准以实现FDR控制。它还允许灵活组合两个关联p值（包括最大值），从而能够构建综合检验。此外，它允许直接使用效应量估计值，无需计算p值。

结果
SMS在多种模拟场景下控制了FDR，同时相对于现有方法（包括HDMT、DACT和DEI-B）实现了显著的灵敏度提升，通常约20个百分点。应用于代谢组学数据集和DNA甲基化数据集进一步证实了这些发现。值得注意的是，SMS在代谢组学数据集中发现了所有现有方法均遗漏的五个合理中介变量。

## Abstract
BackgroundMediation analysis of high-dimensional features, particularly molecular-level omics features, provides important opportunities to uncover biological mechanisms underlying human health and disease. However, two central statistical challenges remain: testing the composite-null hypothesis and maintaining power when the exposure-mediator and mediator-outcome associations differ substantially in statistical significance. Existing methods typically rely on accurate estimation of the proportions of the three null types or on the maximum of the two association p-values, and may not always control the FDR well and may have limited power under imbalanced significance.

MethodsWe propose SMS, a new statistical framework based on symmetric mediation statistics. By exploiting symmetry, SMS calibrates the composite null distribution as a whole for FDR control. It also allows flexible combinations of the two association p-values, including the maximum, and then enables construction of an omnibus test. Moreover, it permits direct use of effect-size estimates, bypassing the need to compute p-values.

ResultsSMS controlled the FDR across a wide range of simulation scenarios while achieving a substantial sensitivity gain, often around 20 percentage points, over existing methods including HDMT, DACT, and DEI-B. Applications to a metabolomics dataset and a DNA methylation dataset further corroborated these findings. Notably, SMS discovered five plausible mediators in the metabolomics dataset that were missed by all existing methods considered.