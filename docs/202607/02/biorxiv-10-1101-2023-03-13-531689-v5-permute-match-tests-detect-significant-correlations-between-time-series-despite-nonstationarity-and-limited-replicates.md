---
title: Permute-match tests detect significant correlations between time series despite nonstationarity and limited replicates
title_zh: Permute-match检验能在非平稳和有限重复情况下检测时间序列间的显著相关性
authors: "Yuan, A. E., Shou, W."
date: 2026-07-01
pdf: "https://www.biorxiv.org/content/10.1101/2023.03.13.531689v5.full.pdf"
tags: ["query:fe"]
score: 7.0
evidence: 非平稳时间序列相关性检测方法
tldr: "时间序列相关性分析中，非平稳性和重复数有限导致标准排列检验的最小p值仅达1/n!，n=3时无法通过0.05阈值。本研究提出permute-match检验，通过匹配置换将最小p值降至2/n^n或1/n^n，且保证假阳性率不超显著性水平。在n=3时可达1/27，显著提升检测能力。应用于斑马鱼数据，证实方向对齐时游速更快，证明了方法的实用性。"
source: biorxiv
selection_source: fresh_fetch
motivation: 现有排列检验因重复数少（如n=3）而p值下界过高（1/6），无法达到常见显著性水平，亟需改进。
method: 提出permute-match检验，通过匹配置换策略将最小可达p值降低至2/n^n或1/n^n。
result: 新检验保证假阳性率不超显著性水平，且下界不保守，n=3时p值可达1/27。
conclusion: 该方法扩展了少重复实验相关性检验的可行性，并在斑马鱼数据中成功验证。
---

## 摘要
研究人员常通过判定观测到的相关性是否强于独立零假设下的预期值来分析时间序列对之间的相关性。然而，时间序列通常是非平稳的，其统计特性随时间变化，导致标准检验无效。若存在足够重复样本，可执行一种置换检验，通过比较重复内相关性与重复间相关性来处理非平稳性。尽管该检验基本无假设要求，但其有效性受限于重复样本数（n），因为其最小p值为1/n!。当n=3时，最小值为1/6，使得0.05等阈值无法达到。这在动物实验中严重限制了其应用，因为n可能低至3。我们提出permute-match检验——一种改进的置换检验，能在强依赖证据下报告更低的p值（2/n^n或1/n^n）。当重复样本独立同分布时，permute-match检验保证假阳性率等于或低于显著性水平。1/n^n的界限并非无根据的保守，因为没有额外假设无法进一步降低。我们使用合成数据验证该方法，并将其应用于一个包含3个独立斑马鱼组的现有数据集，证实了斑马鱼在方向对齐时游动更快的观测结果。

## Abstract
Researchers frequently analyze correlations between pairs of time series by determining whether an observed correlation is stronger than expected under the null hypothesis of independence. However, the time series are often nonstationary, with statistical properties that change over time, thereby making standard tests invalid. If sufficient replicates exist, a trial-swapping permutation test can be performed that handles nonstationarity by comparing within-replicate correlations to between-replicate correlations. Although largely assumption-free, this test is fundamentally limited by the number of replicates (n) because its minimum p-value is 1/n!. With n=3, this minimum is 1/6, rendering thresholds like 0.05 unattainable. This limits its use considerably in animal experiments, where n may be as low as 3. We propose permute-match tests -- modified permutation tests that can report lower p-values of 2/nn or 1/nn under strong evidence of dependence. Permute-match tests guarantee a false positive rate at or below the significance level when replicates are independent and identically distributed. The bound of 1/nn is not gratuitously conservative, since it cannot be further lowered without additional assumptions. We demonstrate our approach using synthetic data and apply it to an existing dataset with 3 independent groups of zebrafish, confirming the observation that zebrafish swim faster when directionally aligned.