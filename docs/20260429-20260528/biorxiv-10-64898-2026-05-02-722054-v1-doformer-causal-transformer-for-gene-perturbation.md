---
title: "DoFormer: Causal Transformer for Gene Perturbation"
title_zh: "DoFormer: 用于基因扰动的因果Transformer"
authors: "Karbalayghareh, A., Paull, E., Califano, A."
date: 2026-05-04
pdf: "https://www.biorxiv.org/content/10.64898/2026.05.02.722054v1.full.pdf"
tags: ["query:tsc"]
score: 8.0
evidence: 无需DAG假设的基因扰动因果学习
tldr: 单细胞转录组因果建模面临观察数据不足、扰动预测困难等挑战，现有方法依赖DAG假设或无法区分观察与干预。本文提出DoFormer因果Transformer，在注意力机制中引入do算子，将扰动基因设为干预值并阻断其关注其他基因，从而区分观察与干预模式。使用生物学损失函数训练，在多项扰动预测指标上显著超越基线模型。该工作强调干预感知架构与生物学目标对于单细胞因果建模的重要性。
source: biorxiv
selection_source: fresh_fetch
motivation: 现有因果推断方法依赖DAG假设且难以整合多模态数据，而转录组基础模型将观察与扰动数据等同处理，限制了扰动预测能力。
method: DoFormer在注意力机制中嵌入因果do算子：将扰动基因设置为干预值，并阻止其关注其他基因，以区分观察与干预机制；结合生物学损失函数训练。
result: 在扰动预测任务上，DoFormer相比基线模型和已有基础模型取得显著性能提升，验证了干预感知架构的有效性。
conclusion: DoFormer通过因果do算子与注意力机制融合，实现了无DAG假设的精准扰动预测，强调了干预感知架构和生物学目标在单细胞基因组学中的关键作用。
---

## 摘要
从单细胞数据中学习因果基因调控机制，并进而预测未见扰动的效果，仍然具有挑战性。仅凭观察性RNA-seq数据不足以进行因果建模，而扰动数据至关重要。经典的因果推断方法通常依赖于不现实的有向无环图（DAG）假设，并且不适用于整合多模态数据。当前的转录组基础模型也通常将观察性和扰动数据等同对待，限制了它们对扰动建模的能力。我们提出了DoFormer，一个不依赖DAG假设的因果多模态Transformer，它利用丰富的扰动数据来准确预测先前未见过的扰动。DoFormer通过在注意力机制中引入因果do算子来实现原则性的计算机内扰动：将受扰基因设置为干预值，并阻止其关注其他基因，从而使模型能够完全区分观察性和干预性模式。我们使用生物学信息的损失函数训练DoFormer，并通过全面的扰动预测指标对其进行评估。与基线模型和先前的基础模型相比，DoFormer显著改进了扰动预测，突显了干预感知架构和生物学基础目标在单细胞基因组学因果建模中的重要性。

## Abstract
Learning causal gene regulatory mechanisms from single-cell data, and thereby predicting the effects of unseen perturbations, remains challenging. Observational RNA-seq data alone is insufficient for causal modeling, whereas perturbational data is essential. Classical causal inference methods often rely on unrealistic directed acyclic graph (DAG) assumptions and are not well suited to integrating multimodal data. Current transcriptomic foundation models also typically treat observational and perturbational data identically, limiting their ability to model perturbations. We present DoFormer, a causal multimodal Transformer that makes no DAG assumptions and leverages rich perturbational data to accurately predict previously unseen perturbations. DoFormer enables principled in silico perturbations by adapting the causal do-operator within the attention mechanism: the perturbed gene is set to the intervention value and prevented from attending to other genes, allowing the model to fully distinguish observational from interventional regimes. We train DoFormer using biologically informed loss functions and evaluate it with comprehensive perturbation prediction metrics. DoFormer substantially improves perturbation prediction relative to baseline and prior foundation models, underscoring the importance of intervention-aware architectures and biologically grounded objectives for causal modeling in single-cell genomics.