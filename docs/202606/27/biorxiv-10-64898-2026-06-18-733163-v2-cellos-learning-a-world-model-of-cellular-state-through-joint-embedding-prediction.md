---
title: "CellOS: Learning a World Model of Cellular State through Joint Embedding Prediction"
title_zh: CellOS：通过联合嵌入预测学习细胞状态的世界模型
authors: "Zhou, Q., Le, Y., Qi, X., Chang, S., Lu, H., Wu, Y., Wang, H., Ran, R., li, x."
date: 2026-06-25
pdf: "https://www.biorxiv.org/content/10.64898/2026.06.18.733163v2.full.pdf"
tags: ["query:tsc"]
score: 6.0
evidence: 因果细胞句子语言建模
tldr: 当前单细胞基础模型仅从单一基因表达视图学习，无法捕获互补的细胞状态信息。CellOS提出多视图框架，通过三阶段训练（因果细胞句子建模、密集到专家混合扩展、LLM-JEPA潜在空间对齐）整合表达与感知视图。在3.905亿个单细胞转录组上训练的12B参数模型，在细胞注释、批次整合和扰动预测任务中全面超越现有模型。该工作为实现表示为中心的虚拟细胞世界模型提供了可扩展方案。
source: biorxiv
selection_source: fresh_fetch
motivation: 现有单细胞基础模型仅从单一表达视图学习，缺乏对互补细胞状态视图的对齐，限制了模型对细胞状态的全面理解。
method: 提出三阶段训练策略：因果细胞句子建模预训练，功能保持的密集到MoE扩展，以及基于LLM-JEPA的潜在空间对齐。
result: 12B参数模型在390.5M单细胞转录组上训练，在细胞注释和扰动预测中超越SOTA，同时保持稳健的批次整合能力。
conclusion: 多视图预测对齐为构建可迁移的AI虚拟细胞提供了可扩展路径，推动了表示为中心的细胞世界模型发展。
---

## 摘要
基于单细胞转录组学习的基础模型对于能够表示、查询和预测细胞状态的人工智能虚拟细胞至关重要。然而，当前大多数单细胞基础模型仅从单一视角的基因表达中学习，并主要通过重构或下一个标记预测进行优化。因此，它们捕捉了表达丰度，但无法明确调和细胞状态的互补视图。在此，我们提出CellOS，一个多视角基础模型，从配对表达和感知视角学习细胞表示。CellOS通过一种可扩展的三阶段训练策略整合互补视图，该策略结合了因果细胞句子语言建模、保持功能的稠密到混合专家扩展以及通过LLM-JEPA目标进行的潜在空间对齐。利用这一框架，我们在3.905亿个单细胞转录组上训练了一个120亿参数的模型。在涵盖细胞状态注释、批次整合和扰动响应预测的多样化基准测试中，CellOS在细胞状态注释和扰动响应预测方面始终优于最先进的单细胞基础模型，同时保持了鲁棒的批次整合。这些结果表明，互补细胞视图之间的预测对齐为以表示为中心的细胞世界模型和可迁移的人工智能虚拟细胞提供了一条可扩展的路径。

## Abstract
Foundation models learned from single-cell transcriptomes are central to the prospect of AI virtual cell that can represent, query and predict cellular state. However, most current single-cell foundation models learn from a single view of gene expression and are optimized primarily through reconstruction or next-token prediction. As a result, they capture expression abundance but cannot explicitly reconcile complementary views of cellular state. Here we present CellOS, a multi-view foundation model that learns cellular representations from paired expression and perception views. CellOS integrates complementary views through a scalable three-stage training strategy that combines causal cell-sentence language modelling, function-preserving dense-to-mixture-of-experts expansion and latent-space alignment via an LLM-JEPA objective. Using this framework, we trained a 12-billion-parameter model on 390.5 million single-cell transcriptomes. Across diverse benchmarks spanning cell-state annotation, batch integration and perturbation-response prediction, CellOS consistently outperformed state-of-the-art single-cell foundation models in cell-state annotation and perturbation-response prediction while preserving robust batch integration. Together, these results suggest that predictive alignment between complementary cellular views provides a scalable path toward representation-centric cellular world models and transferable AI virtual cells.