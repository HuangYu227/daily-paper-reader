---
title: Causal Discovery of Synchronous Neural Oscillations based on Jacobian-informed VAR-LiNGAM
title_zh: 基于Jacobian信息VAR-LiNGAM的同步神经振荡因果发现
authors: "Yokoyama, H., Takeuchi, R., Shimizu, S."
date: 2026-05-01
pdf: "https://www.biorxiv.org/content/10.64898/2026.04.28.721377v1.full.pdf"
tags: ["query:tsc"]
score: 9.0
evidence: 使用VAR-LiNGAM进行时间因果发现
tldr: 现有因果发现方法受Granger因果局限，在线性高斯噪声下难以识别大脑模块网络的因果层次。本文提出j-VAR-LiNGAM方法，将相位耦合振荡器模型估计的Jacobian矩阵融入VAR-LiNGAM算法，在合成和真实神经数据上成功提取因果顺序。从小鼠和人类神经振荡信号中发现与神经生理一致的因果层次结构，为揭示大脑层次信息处理的神经基础提供了新方法。
source: biorxiv
selection_source: fresh_fetch
motivation: 克服线性高斯噪声下Granger因果方法无法识别大脑网络因果层次的缺陷。
method: 提出j-VAR-LiNGAM，融合相位耦合振荡器Jacobian矩阵与VAR-LiNGAM算法。
result: 在合成和真实数据中成功提取因果顺序，小鼠和人类数据中发现与神经生理一致的层次结构。
conclusion: 该方法能揭示大脑网络层次信息处理的神经基础。
---

## 摘要
系统神经科学的主要目标是理解脑网络动力学中的功能映射及其因果关系。一些实验和方法研究表明，脑网络中的功能模块性及其层次信息处理对于理解任务特异性或状态特异性信息流在脑中的功能角色至关重要。然而，由于神经科学研究领域中大多数用于检测有效网络结构的既定技术强烈基于“格兰杰因果关系”视角，现有的专门用于脑网络分析的因果发现方法无法识别脑中模块化网络的因果层次，这归因于伪相关问题和线性系统中观测噪声服从高斯分布时因果方向不可区分性。为了解决这些问题，我们开发了一种针对同步神经动力学的因果发现方法，称为Jacobian信息线性非高斯无环模型“j-VAR-LiNGAM”，通过将从观测神经数据估计的相位耦合振荡器模型确定的Jacobian矩阵的信息纳入VAR-LiNGAM算法中。通过展示该方法能够在合成数据和经验神经观测数据中提取因果顺序，验证了该方法的有效性。此外，通过分析从小鼠和人类获得的观测神经振荡信号，我们确认了我们的方法识别了脑中的因果层次结构，这与神经生理学解释一致。这些发现表明，我们提出的方法可以揭示脑网络中层次信息处理的神经基础。

## Abstract
The primary objective of system neuroscience is to understand the functional mapping and its causation in the dynamics of the brain network. Some experimental and methodological studies suggest that functional modularity and its hierarchical information processing in the brain network are crucial to understanding the functional role of task-specific or state-specific information flow in the brain. However, because most of the established techniques for detecting effective network structures in the neuroscience research field are strongly based on the "Granger causality" perspective, existing causal discovery methods specified for brain network analysis cannot identify the causal hierarchy in the modular network in the brain due to spurious correlation issues and indistinguishability of causal direction under the Gaussianity of observational noise in a linear system. To address the issues, we developed a causal discovery method for synchronous neural dynamics, called the Jacobian-informed linear non-Gaussian acyclic model, "j-VAR-LiNGAM", by incorporating the information of the Jacobian matrix determined from a phase-coupled oscillator model estimated from observed neural data into the VAR-LiNGAM algorithms. The method was validated by showing that it could extract causal ordering in both synthetic data and empirical neural observed data. Moreover, by analyzing the observed neural oscillatory signals obtained from mice and humans, we confirmed that our method identified causally hierarchical structures in the brain, which aligned with the neurophysiological interpretations. These findings suggested that our proposed method can reveal the neural basis of hierarchical information processing in the brain network.