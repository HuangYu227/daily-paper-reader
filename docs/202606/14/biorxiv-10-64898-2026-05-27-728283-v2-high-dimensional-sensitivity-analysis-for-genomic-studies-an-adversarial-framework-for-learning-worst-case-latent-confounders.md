---
title: "High-Dimensional Sensitivity Analysis for Genomic Studies: An Adversarial Framework for Learning Worst-Case Latent Confounders"
title_zh: 基因组研究的高维敏感性分析：一种学习最坏情况潜在混淆变量的对抗性框架
authors: "Lin, Y., Lin, K."
date: 2026-06-08
pdf: "https://www.biorxiv.org/content/10.64898/2026.05.27.728283v2.full.pdf"
tags: ["query:tsc"]
score: 7.0
evidence: 对抗学习最坏情况潜变量混杂用于因果敏感性分析
tldr: 高维基因组研究常受未测量混杂因素干扰，现有方法无法量化发现对混杂的稳健性。本文提出sensGAN对抗框架，通过学习能最大程度消除基因关联的最坏情况潜在变量，系统地探索混杂谱。在模拟中准确恢复潜在结构，优于现有方法。应用于阿尔茨海默病小胶质细胞，成功区分稳健疾病信号与由未测量共病神经病理驱动的假阳性发现，提供了一种定量敏感性分析新范式。
source: biorxiv
selection_source: fresh_fetch
motivation: 高维基因组分析中未测量混杂因素会掩盖疾病特异信号，现有方法无法量化发现的稳健性。
method: 提出sensGAN对抗框架，通过约束预测增益学习最坏情况潜在变量，探索混淆谱。
result: 模拟中恢复潜在结构并优于现有方法；在阿尔茨海默病数据中优先稳健通路，分离共病驱动的信号。
conclusion: sensGAN提供了定量敏感性分析范式，可识别稳健生物标记并揭示混杂敏感基因。
---

## 摘要
高维基因组学研究常常受到未测量的生物学过程的混淆，这些过程掩盖了疾病特异性信号。虽然现有工作流程可以估计这些潜在混淆变量，但它们无法量化发现对假设混淆水平变化的稳健性。我们引入了sensGAN，一种深度学习对抗性框架，通过在新颖的预测增益约束下学习“最坏情况”潜在变量（这些变量可消除最多的基因关联），系统地探索混淆谱。通过识别解释观察效应所需的最小混淆强度，我们的方法将范式转向正式的定量敏感性分析。在多种模拟中，sensGAN准确恢复了潜在结构，并在识别对混淆敏感的基因方面优于现有方法。应用于人类阿尔茨海默病小胶质细胞时，我们的框架优先考虑了稳健的疾病通路，同时成功隔离了由未测量的共现神经退行性病理驱动的信号。我们的方法已公开，存放于GitHub仓库yifanlinz/AD_sensitivity_ICML。

## Abstract
High-dimensional genomics studies are frequently confounded by unmeasured biological processes that obscure disease-specific signals. While existing workflows can estimate these latent confounders, they fail to quantify how robust a discovery is to varying levels of hypothetical confounding. We introduce sensGAN, a deep-learning adversarial framework that systematically explores the confounding spectrum by learning "worst-case" latent variables that nullify the most gene associations under novel predictive-gain constraints. By identifying the minimum confounding strength required to explain away an observed effect, our method shifts the paradigm toward a formal, quantitative sensitivity analysis. In diverse simulations, sensGAN accurately recovers latent structures and outper-forms existing methods in identifying confounder-sensitive genes. Applied to human Alzheimers disease microglia, our framework prioritizes robust disease pathways while successfully isolating signals driven by unmeasured co-occurring neurodegenerative pathologies. Our method is publicly available, deposited at the GitHub repository yifanlinz/AD_sensitivity_ICML.