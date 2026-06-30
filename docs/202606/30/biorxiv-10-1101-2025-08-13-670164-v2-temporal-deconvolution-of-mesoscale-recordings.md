---
title: Temporal Deconvolution of Mesoscale Recordings
title_zh: 中尺度记录的时间反卷积
authors: "Stern, M., Shea-Brown, E."
date: 2026-06-26
pdf: "https://www.biorxiv.org/content/10.1101/2025.08.13.670164v2.full.pdf"
tags: ["query:fe"]
score: 6.0
evidence: 开发了从钙成像时间序列中提取特征的反卷积方法
tldr: 中尺度钙成像记录因钙指示剂动力学掩盖了真实神经活动。本文提出了四种去卷积方法：动态分箱、连续变化、一阶差分和修正维纳滤波。在合成数据和同步荧光-尖峰记录上，这些方法均优于传统的Lucy-Richardson算法。研究表明，准确的时间去卷积对于避免虚假相关性和可靠解释大脑活动至关重要。
source: biorxiv
selection_source: fresh_fetch
motivation: 钙指示剂动力学掩盖了中尺度成像中潜在的神经活动，导致分析结果失真。
method: 开发了四种去卷积方法：动态分箱、连续变化、一阶差分和修正维纳滤波，用于恢复神经元发放率。
result: 四种方法在合成和实测数据上均优于传统Lucy-Richardson算法，并揭示了原始荧光信号会导致虚假脑区间相关性。
conclusion: 准确的时间去卷积是可靠解释中尺度钙成像数据的前提，可避免分析偏差。
---

## 摘要
中尺度钙成像（如宽场成像）能够以高时间分辨率记录大范围脑区的神经元活动。然而，由于这些记录捕捉的是钙指示剂荧光发射的光信号，潜在的神经活动被指示剂的时域动力学所掩盖。本文开发并评估了四种反卷积方法，以从宽场成像记录的荧光迹中恢复神经元放电率。这些方法——动态分箱（使用自适应离散时间窗口）、连续变化（估计平滑放电率）、一阶差分（提供高效估计）以及改进的Wiener滤波器（对大幅度的荧光强度变化具有鲁棒性）——在合成数据和同时记录的荧光-锋电位数据上均一致优于先前使用的自适应Lucy-Richardson算法。关键的是，我们证明在高级分析方法中使用原始荧光信号会产生扭曲的结果，包括脑区间活动相关性被虚假地放大。这凸显了准确的时间反卷积对于可靠解释脑活动的重要性。

## Abstract
1Mesoscale calcium recordings, such as wide-field imaging, enable high-temporal-resolution recordings of neuronal activity across extensive brain regions. However, because these recordings capture light emitted by calcium indicator fluorescence, the underlying neural activity is obscured by the temporal dynamics of the indicators. Here, we develop and evaluate four deconvolution methods to recover neuronal spiking rates from fluorescence traces recorded in wide-field imaging. The methods--Dynamically-Binning (using adaptive discrete-time bins), Continuously-Varying (estimating smooth spiking rates), First-Differences (providing efficient estimation), and a modified Wiener Filter (robust to large fluorescence magnitude variations)-consistently outperform the previously used adapted Lucy-Richardson algorithm on both synthetic data and simultaneous fluorescence-spike recordings. Critically, we demonstrate that using raw fluorescence signals in advanced analysis methods can yield distorted results, including spuriously inflated correlations between brain regions activity. This highlights the necessity of accurate temporal deconvolution for reliable interpretation of brain activity.