---
title: Performance Attribution in pLM-Based Biological Relation Prediction
title_zh: 基于蛋白质语言模型的生物关系预测中的性能归因
authors: "Zhu, K., Zhao, W., Zhang, Y., Xia, Z."
date: 2026-07-02
pdf: "https://www.biorxiv.org/content/10.64898/2026.06.28.735130v1.full.pdf"
tags: ["query:fe"]
score: 7.0
evidence: 使用冻结蛋白质语言模型进行生物关系预测
tldr: 针对pLM在生物关系预测中的性能归因问题，通过MetaESI、DeepGNHV和SAGEPhos三个案例，采用冻结pLM全输入基线、端点/位点限制控制、干净先验控制等方法进行系统分析。结果显示，冻结ESM2输入配合简单下游模型可达较好性能，但自标签排除的频率控制（无需序列嵌入）几乎达到全输入性能，且GARD池化无优势。标签打乱使判别力降为随机，而端点冷诊断显示性能下降。该研究揭示了基准性能与归因的差异，强调需要匹配控制来支持架构、关系或泛化性声明。
source: biorxiv
selection_source: fresh_fetch
motivation: 探究pLM在生物关系预测中高性能的信息来源，区分架构贡献与数据泄漏等混杂因素。
method: 对三个案例采用冻结pLM全输入基线、端点/位点限制控制、干净先验控制及GARD池化对比实验。
result: 自标签排除的频率控制AUROC 0.846，接近冻结ESM2全输入的0.827；标签打乱使AUROC降至~0.5。
conclusion: 基准性能并非等价于生物学学习，正确归因需匹配控制实验。
---

## 摘要
蛋白质语言模型(pLMs)在生物关系预测任务中展现出强大的基准性能，但聚合指标无法识别哪些信息源支撑了该性能。我们研究了三个案例——MetaESI、DeepGNHV和SAGEPhos，使用了冻结pLM全输入基线、端点或位点限制对照、干净训练集先验对照以及限制匹配的选择器对照。冻结pLM衍生输入结合通用下游学习器在MetaESI当前全输入重复中达到AUROC/AUPRC 0.827/0.703，DeepGNHV两端点基线为0.922/0.708，SAGEPhos为0.896/0.893。限制对照保留了任务依赖信号。最值得注意的是，在行划分下，排除自身标签的MetaESI端点频率对照达到0.846/0.676，尽管未使用序列嵌入，数值上接近冻结ESM2全输入参考。干净的完整目录DeepGNHV端点先验和SAGEPhos激酶/底物/位点窗口先验提供了补充诊断，而非直接架构贡献估计。在单独的固定冻结池化LightGBM实验中，GARD选择的池化并未显示出比计数匹配的随机标记池化更高的观测性能。端点冷诊断显示性能下降，而训练标签洗牌将区分度降至接近随机水平；在案例研究中无法获得硬负或匹配负样本以及家族或同源感知评估。这些发现并不诊断泄露、暗示记忆、排除生物学习或使评估模型无效。相反，它们表明基准效用和性能归因是不同的：架构特定、关系特定、选择器特定以及泛化声明需要与解释相匹配的对照。

## Abstract
Protein language models (pLMs) have enabled strong benchmark performance in biological relation-prediction tasks, but aggregate metrics do not identify which sources of information support that performance. We examined three case studies-MetaESI, DeepGNHV, and SAGEPhos-using frozen pLM full-input baselines, endpoint- or site-restricted controls, clean train-derived prior controls, and a restriction-matched selector control. Frozen pLM-derived inputs coupled to generic downstream learners reached AUROC/AUPRC of 0.827/0.703 for the current MetaESI full-input rerun, 0.922/0.708 for a DeepGNHV two-endpoint baseline, and 0.896/0.893 for SAGEPhos. Restricted controls retained task-dependent signal. Most notably, a self-label-excluding MetaESI endpoint-frequency control reached 0.846/0.676 under the row split, numerically close to the frozen ESM2 full-input reference despite using no sequence embeddings. Clean full-catalog DeepGNHV endpoint priors and SAGEPhos kinase/substrate/site-window priors provided supplementary diagnostics rather than direct architecture-contribution estimates. In a separate fixed frozen-pooling LightGBM experiment, GARD-selected pooling did not show higher observed performance than count-matched random token pooling. Endpoint-cold diagnostics showed performance degradation, while train-label shuffling returned discrimination to approximately chance; hard- or matched-negative and family- or homology-aware evaluations were not available across the case studies. These findings do not diagnose leakage, imply memorization, exclude biological learning, or invalidate the evaluated models. Rather, they show that benchmark utility and performance attribution are distinct: architecture-specific, relation-specific, selector-specific, and generalization claims require controls matched to the interpretation being made.