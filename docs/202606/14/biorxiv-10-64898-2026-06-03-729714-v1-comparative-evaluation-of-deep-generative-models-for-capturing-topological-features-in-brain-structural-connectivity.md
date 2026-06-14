---
title: Comparative Evaluation of Deep Generative Models for Capturing Topological Features in Brain Structural Connectivity
title_zh: 深度生成模型捕获脑结构连接拓扑特征的比较评估
authors: "Kumada, C., Hiroyasu, T., Hiwa, S."
date: 2026-06-08
pdf: "https://www.biorxiv.org/content/10.64898/2026.06.03.729714v1.full.pdf"
tags: ["query:tsc"]
score: 6.0
evidence: "深度生成模型（VAE, WGAN-GP, DDPM）在结构化数据生成中的比较评估，方法可迁移至时间序列"
tldr: 脑结构连接数据稀缺限制了机器学习应用。本研究系统比较了VAE、WGAN-GP和DDPM三种深度生成模型在生成此类数据时捕捉拓扑特征的能力。WGAN-GP在多种评估下表现稳定，适合作为基线；VAE和DDPM特定场景表现好但敏感。所有模型均难以再现全局结构约束如平面性，表明标准生成模型不足以捕捉复杂拓扑，需在训练或生成中融入结构先验。
source: biorxiv
selection_source: fresh_fetch
motivation: 脑结构连接数据有限，需要评估不同生成模型对拓扑特征的捕捉能力以指导数据增强。
method: 比较VAE、WGAN-GP和DDPM，使用合成与真实数据，基于图论指标和邻接矩阵视觉检查评估生成质量。
result: WGAN-GP性能稳定，VAE和DDPM敏感；所有模型难以完全重现全局约束如平面性。
conclusion: WGAN-GP可作为基线，但标准生成模型不足以捕捉复杂拓扑，需将目标结构属性融入生成过程。
---

## 摘要
结构连接数据对于脑网络分析至关重要，但基于结构连接的机器学习常受限于数据可用性不足，影响模型的泛化性和鲁棒性。尽管使用深度生成模型进行数据增强日益受到关注，但不同模型如何捕获结构连接数据的复杂拓扑特征仍不明确。为阐明深度生成模型在结构连接生成中的学习特性，本研究比较了三种代表性模型：变分自编码器、带梯度惩罚的Wasserstein GAN以及去噪扩散概率模型。我们使用已知特征的合成数据集和真实的结构连接数据系统评估了这些模型。通过图论指标比较和生成邻接矩阵的可视化检查评估生成质量。WGAN-GP在数据集和指标上表现出相对稳定的性能，未出现跨评估设置的严重性能下降。相比之下，VAE和DDPM在特定方面表现良好，但对数据特征更为敏感。这些发现表明，WGAN-GP可作为未来结构连接数据增强研究中最均衡的基线模型，而VAE和DDPM则可能根据目标应用和感兴趣的拓扑特性而有用。此外，由于所有模型都难以完全再现平面性等严格全局约束，我们的结果表明标准生成模型可能不足以捕获结构连接数据的复杂拓扑特征。这凸显了将所需结构特性纳入训练或生成过程的重要性。

## Abstract
Structural connectivity (SC) data are crucial for brain network analysis, but SC-based machine learning often suffers from limited data availability, hindering model generalization and robustness. Although data augmentation using deep generative models has attracted increasing attention, it remains unclear how different models capture the complex topological features of SC data. To clarify the learning characteristics of deep generative models for SC generation, this study compares three representative models: variational autoencoder (VAE), Wasserstein GAN with gradient penalty (WGAN-GP), and denoising diffusion probabilistic models (DDPM). We systematically evaluated these models using both synthetic datasets with known characteristics and real-world SC data. Generation quality was assessed using graph-theoretic metric comparisons and visual inspection of the generated adjacency matrices. WGAN-GP showed relatively stable performance across datasets and metrics, without severe performance degradation across evaluation settings. In contrast, VAE and DDPM performed well in specific aspects but were more sensitive to data characteristics. These findings suggest that WGAN-GP may serve as the most balanced baseline for future SC data augmentation studies, whereas VAE and DDPM may be useful depending on the target application and structural properties of interest. Furthermore, because all models struggled to fully reproduce strict global constraints such as planarity, our results suggest that standard generative models may be insufficient to capture the complex topological features of SC data. This highlights the importance of incorporating the desired structural properties into the training or generation process.