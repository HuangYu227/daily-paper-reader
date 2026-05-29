---
title: "Cell-CLIP: Multi-algorithm causal discovery of directed cell program interaction networks from single-cell transcriptomics"
title_zh: Cell-CLIP：从单细胞转录组学进行多算法因果推断以发现定向细胞程序相互作用网络
authors: "Al-Tal, M. K. F., Liu, X., Zhou, J."
date: 2026-05-22
pdf: "https://www.biorxiv.org/content/10.64898/2025.12.01.691666v2.full.pdf"
tags: ["query:tsc"]
score: 9.0
evidence: 多算法因果发现流程用于生物网络
tldr: "细胞通讯网络调控组织功能，但现有工具无法区分直接因果与混淆关联。本文提出Cell-CLIP框架，整合掩码感知JASMINE活性评分、五种因果发现算法、方向保持bootstrap聚合与联合因果推理。在611例多表型肺图谱上，跨队列联合因果推理图以100%召回率、75%方向准确率恢复所有可评估已知边，且无禁忌方向违规。该框架为从单细胞转录组推断有向细胞程序网络提供假设生成工具。"
source: biorxiv
selection_source: fresh_fetch
motivation: 现有细胞通讯工具依赖静态配体-受体数据库或相关性分析，无法从单细胞转录组数据推断直接因果。
method: 结合掩码感知JASMINE活性评分、PC/GES/FCI/DirectLiNGAM/GRaSP五种算法、方向保持bootstrap聚合与联合因果推理（JCI），并系统扫描超参数。
result: "跨队列图恢复8/8已知边（100%召回），方向准确率75%，零禁忌违规；单队列图召回100%，方向准确率62.5%，优于零插值基线。"
conclusion: Cell-CLIP可从单细胞图谱推断有向细胞程序网络，生成因果假设，但需实验验证。
---

## 摘要
细胞间通信网络调控健康和疾病状态下的组织功能，但现有计算工具依赖于静态配体-受体数据库或基于相关性的分析，无法区分直接因果关系与混杂或间接关联。我们提出Cell-CLIP（细胞因果学习与推断管线），这是一个模块化框架，结合了（i）基于掩码的患者级JAS-MINE活性评分，在原始活性空间中采用低百分位插补；（ii）五种互补的因果发现算法——PC、GES、FCI、DirectLiNGAM和GRaSP，每种算法均接收同一掩码JASMINE矩阵的算法匹配的逐列变换；（iii）带方向保持的Bootstrap聚合与加权两阶段共识；（iv）联合因果推断（JCI），通过情境指示符实现患者队列的原则性合并；以及（v）残差独立性（RESIT）方向审计，所有步骤均在系统性的三乘三乘三超参数扫描下评估。应用于包含正常组织、COVID-19肺炎和肺癌的611名患者多表型肺图谱时，通过将患者分层为正常、COVID-19和肿瘤情境后再合并构建的跨队列联合因果推断图，在评估的8条可验证基准真实边中恢复100%（8/8），方向准确率为75.0%，且对三条独立策划的禁止方向零违规——这是涵盖7种队列/合并配置、27种超参数设置和3种共识类型的全面消融系列中唯一同时达到所有三个最优帕累托拐点的配置。单队列通用跨表型图（覆盖全部611名患者的12个跨表型程序）在相同的系统性超参数扫描和低百分位插补下，同样实现了100%的可验证召回率，方向准确率为62.5%，零禁止违规，所有指标均优于该管线的早期零插补基线配置（敏感性分析部分）。我们进一步表明，对疾病扩展合并队列（将COVID-19和癌症扩展程序集应用于所有611名患者）的单队列因果推断恢复了强骨架召回率（可验证率35.0%-55.2%），但遭受结构性方向崩溃（方向准确率降至14.3%，并集禁止率高达60%），这是由于对正常加疾病的异质患者群体进行队列内平均所致；患者分层的联合因果推断池消除了这种崩溃，且无需改变底层算法。Cell-CLIP提供了一个假设生成框架，用于从患者级scRNA-seq图谱推断定向细胞程序网络，由于观察性数据的局限性，所有报告的关系均需实验验证。

## Abstract
Cell-cell communication networks govern tissue function in health and disease, yet existing computational tools rely on static ligand-receptor databases or correlation-based analyses that cannot distinguish direct causal relationships from confounded or indirect associations. We introduce Cell-CLIP (Cellular Causal Learning and Inference Pipeline), a modular framework that combines (i) mask-aware patient-level JAS-MINE activity scoring with low-percentile imputation in raw activity space, (ii) five complementary causal-discovery algorithms -- PC, GES, FCI, DirectLiNGAM, and GRaSP -- each fed an algorithm-matched per-column transform of the same masked JASMINE matrix, (iii) direction-preserving bootstrap aggregation with a weighted two-phase consensus, (iv) Joint Causal Inference (JCI) for principled pooling of patient cohorts via context indicators, and (v) a residual-independence (RESIT) direction audit, all evaluated under a systematic three-by-three-by-three hyperparameter sweep. Applied to a 611-patient multi-phenotype lung atlas spanning normal tissue, COVID-19 pneumonia, and lung cancer, the cross-cohort joint-causal-inference graph constructed by stratifying patients into normal, COVID-19, and tumour contexts before pooling recovers 100% (8 of 8) of evaluable curated ground-truth edges with 75.0% direction accuracy and zero forbidden-orientation violations against three independently curated forbidden orientations -- the only configuration in a comprehensive ablation series spanning 7 cohort/pool configurations, 27 hyperparameter settings, and 3 consensus types to simultaneously reach all three optimal Pareto corners. The single-cohort universal cross-phenotype graph (12 cross-phenotype programs over the full 611-patient atlas) similarly achieves 100% evaluable recall with 62.5% direction accuracy and zero forbidden violations under the same systematic hy-perparameter sweep with low-percentile imputation, exceeding an earlier zero-imputation baseline configuration of the pipeline on every metric (the Sensitivity analysis section). We further show that single-cohort causal inference on the disease-extended pooled cohorts (which apply the COVID- and cancer-extended pro-gram sets to all 611 patients) recovers strong skeleton recall (35.0%-55.2% evaluable) but suffers a structural direction collapse (down to 14.3% direction accuracy and 60% forbidden rate at union) caused by within-cohort averaging over heterogeneous normal-plus-disease patient populations; the patient-stratified joint-causal-inference pool dissolves this collapse without altering the underlying algorithms. Cell-CLIP provides a hypothesis-generating framework for inferring directed cell-program networks from patient-level scRNA-seq atlases, with all reported relationships requiring experimental validation due to observational data limitations.

---

## 论文详细总结（自动生成）

# 论文详细中文总结

## 1. 论文的核心问题与整体含义（研究动机和背景）

- **研究动机**：细胞间通信网络对于理解健康和疾病状态下的组织功能至关重要。然而，现有计算工具或者依赖于静态的配体-受体数据库，或者仅进行基于相关性的分析，无法区分直接的因果关系与混杂因素或间接关联。
- **核心问题**：如何从患者级别的单细胞转录组图谱（scRNA-seq）中推断出**有向的**（即因果方向明确的）细胞程序相互作用网络，而不仅仅是无向的关联。
- **整体含义**：提出一种名为 **Cell-CLIP**（细胞因果学习与推断管线）的模块化框架，旨在作为假设生成工具，为后续实验验证提供因果候选关系。该工作聚焦于多表型肺图谱（正常组织、COVID-19肺炎、肺癌），展示了从单细胞数据推断因果网络的可能性。

## 2. 论文提出的方法论：核心思想、关键技术细节

### 核心思想
- 将**因果发现算法**与**单细胞活性评分**相结合，通过多算法集成、方向保持聚合、联合因果推断（JCI）和残差方向审计，从观测性单细胞数据中推断有向网络。
- 通过患者分层（按表型）后再合并，避免因异质性导致的因果结构崩溃。

### 关键技术细节（算法流程）
1. **掩码感知患者级JASMINE活性评分**：在原始活性空间中采用低百分位插补（low-percentile imputation），生成每个患者的活性矩阵。
2. **五种互补因果发现算法**：PC、GES、FCI、DirectLiNGAM、GRaSP。每种算法接收同一掩码JASMINE矩阵但经过**算法匹配的逐列变换**（per-column transform），以适配不同算法的假设。
3. **方向保持Bootstrap聚合与加权两阶段共识**：通过Bootstrap重采样生成多个因果图，采用方向保持策略聚合，并经过两阶段加权共识得到最终的图结构。
4. **联合因果推断（JCI）**：通过引入情境指示符（context indicators）将不同患者队列（如正常、COVID-19、肿瘤）原则性地合并，进行联合因果推断。
5. **残差独立性方向审计（RESIT）**：对推断的因果方向进行独立审计，确保方向合理性。
6. **系统性超参数扫描**：采用三乘三乘三（3×3×3）的超参数网格搜索，覆盖不同算法参数配置。

## 3. 实验设计：数据集/场景、基准（benchmark）、对比方法

- **数据集**：包含611名患者的多表型肺图谱，涵盖正常组织、COVID-19肺炎、肺癌三种状态。程序集包括12个跨表型程序（跨表型图谱）以及扩展的COVID-19和癌症程序集。
- **实验场景**：
  - **跨队列联合因果推断**：将患者按正常、COVID-19、肿瘤分层后通过JCI合并，构建跨队列图。
  - **单队列通用跨表型图**：将全部611名患者作为单一队列，应用12个跨表型程序进行因果推断。
  - **疾病扩展合并队列**：将COVID-19和癌症扩展程序集应用于所有611名患者，作为单队列（未分层）进行因果推断，并与分层后的JCI版本对比。
- **基准（ground truth）**：可评估的基准真实边8条，以及三条独立策划的禁止方向（forbidden orientations）。这些源自领域先验知识或文献。
- **对比方法**：内部消融实验，包括：
  - 7种队列/合并配置（如单队列、分层后JCI、不同共识类型等）
  - 27种超参数设置（3×3×3扫描）
  - 3种共识类型（如加权两阶段共识 vs 早期零插值基线配置）
  - 与早期零插值基线（zero-imputation baseline）对比。
- **评估指标**：
  - 召回率（recall）：恢复基准边的比例
  - 方向准确率（direction accuracy）：正确方向的比例
  - 禁止方向违规率（forbidden orientation violations）：对预设禁止方向的违反情况
  - 骨架召回率（skeleton recall）：不考虑方向只考虑边存在性的召回率

## 4. 资源与算力

- **文中未明确说明**所使用的GPU型号、数量或训练时长。仅提到该方法为“模块化框架”，但未提供任何计算资源详细信息。需要指出：该论文来自预印本，可能未包含算力细节。

## 5. 实验数量与充分性

- **实验数量**：非常丰富。覆盖了：
  - 7种队列/合并配置
  - 27种超参数设置
  - 3种共识类型
  - 单独针对每个表型（正常、COVID-19、肿瘤）以及跨表型联合的分析
  - 对比了早期零插值基线
  - 敏感性分析部分还探讨了疾病扩展合并队列的崩溃现象及JCI的恢复效果。
- **充分性与公平性**：实验设计系统、全面。采用了多角度消融，覆盖了不同算法、不同合并策略、不同超参数。公平性体现在：所有配置均在同一数据集、相同评估指标下比较，且发现只有跨队列联合因果推断图同时达到三个最优帕累托拐点（100%召回、75%方向准确率、零禁止违规）。实验客观地指出了单队列在异质性数据上的方向崩溃问题，并展示了JCI的改善。

## 6. 论文的主要结论与发现

1. **跨队列联合因果推断图**（患者分层后JCI）：在8条可评估基准真实边中达到100%召回率，方向准确率75.0%，且对三条独立策划的禁止方向零违规。这是消融系列中唯一同时满足所有三个最优帕累托拐点的配置。
2. **单队列通用跨表型图**（12个程序覆盖611名患者，使用低百分位插补）：同样达到100%可验证召回率，方向准确率62.5%，零禁止违规，优于早期零插值基线。
3. **疾病扩展合并队列的单队列因果推断**：虽然骨架召回率尚可（35.0%-55.2%），但方向准确率急剧下降至14.3%，且并集禁止率高达60%。这是由于对正常+疾病的异质性患者群体进行**队列内平均**导致的结构性方向崩溃。
4. **患者分层的JCI池化消除了这种崩溃**，无需改变底层算法。
5. **结论**：Cell-CLIP提供了一个假设生成框架，可用于从患者级scRNA-seq图谱推断有向细胞程序网络。但所有报告的关系均需实验验证，因为数据来自观测性研究。

## 7. 优点：方法或实验设计上的亮点

- **模块化与多算法集成**：融合五种不同类型（基于约束、基于分数、基于函数等）的因果发现算法，充分利用各自优势，并通过集成提高鲁棒性。
- **方向保持Bootstrap聚合与加权共识**：在聚合过程中保持方向信息，避免边方向被平均模糊。
- **联合因果推断（JCI）** 创新性地将患者表型作为情境指示符，实现跨队列原则性合并，有效解决了异质性数据中的平均偏差问题。
- **系统性超参数扫描**：3×3×3网格搜索确保了结果的鲁棒性，避免了人工调参的偶然性。
- **全面消融实验**：覆盖队列配置、超参数、共识类型、基线对比，实验设计严谨，发现都具有解释性（如方向崩溃及其解决方案）。
- **客观承认局限性**：明确指出观测数据无法完全替代因果推断结论，需要实验验证。

## 8. 不足与局限

- **实验覆盖方面**：仅基于一个多表型肺图谱数据集（611例患者），泛化性尚未验证。不同组织类型、疾病状态或数据平台可能表现不同。
- **基准真实边数量较少**：仅8条可评估边和3条禁止方向，可能不足以全面评估方法性能。更多经过实验验证的基准边会有助于更可靠的结论。
- **缺乏与其他现有细胞通讯推断工具（如CellChat、NicheNet等）的直接比较**：论文仅进行了内部消融，未与主流方法对比，因此无法证明Cell-CLIP的绝对优势。
- **超参数扫描范围有限**：3×3×3虽然系统，但可能未覆盖最优配置的全部空间。更宽的搜索或自动调参可能提升表现。
- **计算资源与效率未讨论**：未说明运行时间或内存消耗，对于大规模图谱的实用性存疑。
- **应用限制**：方法依赖于JASMINE活性评分，可能受限于基因程序定义的质量；因果发现算法假设无隐藏混杂或其他结构假设（如非高斯性、无反馈等），在真实生物系统中可能不成立。

（完）
