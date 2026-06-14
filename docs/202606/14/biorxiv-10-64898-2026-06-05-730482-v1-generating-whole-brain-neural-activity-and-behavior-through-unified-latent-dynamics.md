---
title: Generating whole-brain neural activity and behavior through unified latent dynamics
title_zh: 通过统一潜在动力学生成全脑神经活动和行为
authors: "Nuzzi, D., Mattia, M., Pezzulo, G."
date: 2026-06-10
pdf: "https://www.biorxiv.org/content/10.64898/2026.06.05.730482v1.full.pdf"
tags: ["query:tsc"]
score: 7.0
evidence: 通过统一潜在动力学生成神经活动和行为时间序列
tldr: 神经科学面临高维神经活动与行为如何从共享底层动态涌现的挑战。本文提出NEBULA框架，通过学习统一潜在动态联合建模全脑神经活动与行为。在线虫全脑记录上，该框架能够长时程生成神经和行为轨迹，并实现真实行为模拟与虚拟干预。结果揭示了行为相关的动态转换点，为可扩展的虚拟实验奠定了基础。
source: biorxiv
selection_source: fresh_fetch
motivation: 解决高维神经活动与行为如何从共享底层动态涌现的难题，实现脑-行为数字孪生。
method: 提出NEBULA生成框架，利用线虫全脑记录学习统一潜在动态，联合建模神经活动与行为。
result: 实现长时程轨迹生成、真实行为模拟，并通过扰动发现行为转换点，导向干预可操控状态。
conclusion: 建立了连接大脑动态与行为的框架，为神经科学的可扩展虚拟实验提供基础。
---

## 摘要
理解高维神经活动和行为如何从共享的潜在动力学中涌现仍是神经科学的一个基本挑战。解决这一问题对于实现能够忠实再现和预测生命系统多尺度脑-行为动态的数字孪生至关重要。本文提出了NEBULA（通过统一潜在动力学进行神经与行为建模），这是一个联合建模全脑神经活动和行为的生成框架。利用秀丽隐杆线虫的全脑记录，该模型学习了一个统一的潜在动力学结构，支持长时间范围内的神经与行为轨迹生成、行为的逼真模拟以及定向虚拟干预。对所学动力学的扰动揭示了与行为相关的转折点，而操控干预则无需重新训练即可实现对神经和行为状态的控制操作。这些结果为将脑动力学与生物体行为联系起来建立了一个框架，并为神经科学中的可扩展虚拟实验奠定了基础。

## Abstract
Understanding how high-dimensional neural activity and behavior emerge from shared underlying dynamics remains a fundamental challenge in neuroscience. Addressing this problem is key to enabling digital twins that can faithfully reproduce and predict the multiscale brain-behavior dynamics of living systems. Here we present NEBULA (NEural and Behavioral modeling through Unified LAtent dynamics), a generative framework that jointly models whole-brain neural activity and behavior. Using brain-wide recordings from C. elegans, the model learns a unified latent dynamical structure that supports long-horizon generation of neural and behavioral trajectories, realistic simulations of behavior, and targeted virtual interventions. Perturbations of the learned dynamics reveal behaviorally relevant transition points, whereas steering interventions enable controlled manipulation of neural and behavioral states without retraining. These results establish a framework for linking brain dynamics to behavior in a living organism and provide a foundation for scalable virtual experimentation in neuroscience.