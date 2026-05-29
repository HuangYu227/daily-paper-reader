---
title: "Cell-CLIP: Multi-algorithm causal discovery of directed cell program interaction networks from single-cell transcriptomics"
title_zh: Cell-CLIP：从单细胞转录组学中多算法因果发现定向细胞程序相互作用网络
authors: "Al-Tal, M. K. F., Liu, X., Zhou, J."
date: 2026-05-28
pdf: "https://www.biorxiv.org/content/10.64898/2025.12.01.691666v3.full.pdf"
tags: ["query:tsc"]
score: 9.0
evidence: 从单细胞转录组时间序列中进行多算法因果发现
tldr: "细胞通讯网络影响组织功能，但现有工具难以从单细胞转录组中推断因果关系。Cell-CLIP框架结合JASMINE活性评分、五种因果发现算法、方向保留bootstrap聚合及联合因果推断，在611患者多表型肺图谱上实现100%基础真值边召回，方向准确率75%，零禁止方向违反。该框架为从患者级scRNA-seq推断有向细胞程序网络提供假设生成工具，所有结果需实验验证。"
source: biorxiv
selection_source: fresh_fetch
motivation: 现有方法依赖静态配体受体数据库或相关性分析，无法区分直接因果关系与混淆或间接关联。
method: 提出Cell-CLIP，整合JASMINE活性评分、五种因果发现算法、方向保留bootstrap聚合及联合因果推断。
result: "跨队列联合推断恢复100%评估基础真值边，方向准确率75%，零禁止方向违反；单队列图谱同样达100%召回。"
conclusion: Cell-CLIP为从患者级scRNA-seq推断有向细胞程序网络提供假设生成框架，但因果关系需实验验证。
---

## 摘要
细胞间通讯网络控制着健康和疾病状态下的组织功能，然而现有的计算工具依赖于静态的配体-受体数据库或基于相关性的分析方法，这些方法无法区分直接的因果关联与混杂或间接关联。我们提出Cell-CLIP（细胞因果学习与推断流水线），这是一个模块化框架，结合了：（i）基于掩码的患者水平JAS-MINE活性评分与原始活性空间中的低百分位数插补；（ii）五种互补的因果发现算法——PC、GES、FCI、DirectLiNGAM和GRaSP，每种算法输入相同掩码JASMINE矩阵的算法匹配的逐列变换；（iii）带有加权两阶段共识的保持方向的Bootstrap聚合；（iv）联合因果推断（JCI）通过上下文指标实现患者队列的原则性合并；以及（v）残差独立性（RESIT）方向审核，所有步骤均在系统的三乘三乘三超参数扫描下进行评估。应用于一个包含611名患者的多表型肺图谱（涵盖正常组织、COVID-19肺炎和肺癌），通过将患者分层为正常、COVID-19和肿瘤背景再合并构建的跨队列联合因果推断图，在可评估的精选真实关系边中恢复了100%（8/8），方向准确率为75.0%，并且针对三个独立精选的禁止方向没有违反任何禁忌方向——这是在涵盖7种队列/合并配置、27种超参数设置和3种共识类型的全面消融系列中唯一同时达到所有三个最优帕累托边角的配置。单队列通用跨表型图（覆盖完整611名患者图谱的12种跨表型程序）在相同系统的超参数扫描和低百分位数插补下，同样实现了100%的可评估召回率，方向准确率为62.5%，且无禁忌方向违反，在各项指标上均优于该流水线的早期零插补基线配置（敏感性分析部分）。我们进一步表明，对疾病扩展的合并队列（将COVID-19和癌症扩展的程序集应用于所有611名患者）进行单队列因果推断，恢复了较强的骨架召回率（可评估的35.0%-55.2%），但遭受了结构方向崩溃（方向准确率降至14.3%，并集中禁忌率为60%），这是由于在同一队列内对异质的正常加疾病患者群体进行平均所致；而患者分层的联合因果推断池消除了这种崩溃，且无需改变底层算法。Cell-CLIP提供了一个假设生成的框架，用于从患者水平的scRNA-seq图谱中推断定向细胞程序网络，由于观察数据的局限性，所有报告的关系均需实验验证。

## Abstract
Cell-cell communication networks govern tissue function in health and disease, yet existing computational tools rely on static ligand-receptor databases or correlation-based analyses that cannot distinguish direct causal relationships from confounded or indirect associations. We introduce Cell-CLIP (Cellular Causal Learning and Inference Pipeline), a modular framework that combines (i) mask-aware patient-level JAS-MINE activity scoring with low-percentile imputation in raw activity space, (ii) five complementary causal-discovery algorithms -- PC, GES, FCI, DirectLiNGAM, and GRaSP -- each fed an algorithm-matched per-column transform of the same masked JASMINE matrix, (iii) direction-preserving bootstrap aggregation with a weighted two-phase consensus, (iv) Joint Causal Inference (JCI) for principled pooling of patient cohorts via context indicators, and (v) a residual-independence (RESIT) direction audit, all evaluated under a systematic three-by-three-by-three hyperparameter sweep. Applied to a 611-patient multi-phenotype lung atlas spanning normal tissue, COVID-19 pneumonia, and lung cancer, the cross-cohort joint-causal-inference graph constructed by stratifying patients into normal, COVID-19, and tumour contexts before pooling recovers 100% (8 of 8) of evaluable curated ground-truth edges with 75.0% direction accuracy and zero forbidden-orientation violations against three independently curated forbidden orientations -- the only configuration in a comprehensive ablation series spanning 7 cohort/pool configurations, 27 hyperparameter settings, and 3 consensus types to simultaneously reach all three optimal Pareto corners. The single-cohort universal cross-phenotype graph (12 cross-phenotype programs over the full 611-patient atlas) similarly achieves 100% evaluable recall with 62.5% direction accuracy and zero forbidden violations under the same systematic hy-perparameter sweep with low-percentile imputation, exceeding an earlier zero-imputation baseline configuration of the pipeline on every metric (the Sensitivity analysis section). We further show that single-cohort causal inference on the disease-extended pooled cohorts (which apply the COVID- and cancer-extended pro-gram sets to all 611 patients) recovers strong skeleton recall (35.0%-55.2% evaluable) but suffers a structural direction collapse (down to 14.3% direction accuracy and 60% forbidden rate at union) caused by within-cohort averaging over heterogeneous normal-plus-disease patient populations; the patient-stratified joint-causal-inference pool dissolves this collapse without altering the underlying algorithms. Cell-CLIP provides a hypothesis-generating framework for inferring directed cell-program networks from patient-level scRNA-seq atlases, with all reported relationships requiring experimental validation due to observational data limitations.

---

## 论文详细总结（自动生成）

### 1. 论文的核心问题与整体含义（研究动机和背景）

- **研究动机**：细胞间通讯网络在健康和疾病状态中调控组织功能，但现有计算工具（如基于静态配体-受体数据库或相关性分析的方法）只能识别共表达或关联，无法区分直接的因果关系与由混杂变量或间接路径导致的伪关联。
- **背景意义**：单细胞转录组学（scRNA-seq）提供了细胞状态的高分辨率快照，但从观察性数据中推断方向性因果网络是统计上的挑战。本文旨在填补这一空白，提出一个假设驱动框架，用于从患者水平的scRNA-seq图谱中推断定向细胞程序相互作用网络。

### 2. 论文提出的方法论：核心思想、关键技术细节

- **核心思想**：Cell-CLIP (Cellular Causal Learning and Inference Pipeline) 是一个模块化框架，通过整合多种因果发现算法、方向保持的Bootstrap聚合以及联合因果推断（JCI）策略，从患者级别的单细胞转录组数据中稳健地推断有向细胞程序网络。
- **关键技术细节**：
  1. **活性评分与插补**：使用掩码感知的JASMINE方法计算患者水平的细胞程序活性得分，并在原始活性空间中进行低百分位数插补（low-percentile imputation），以减少缺失值和噪声。
  2. **五种互补因果发现算法**：对同一掩码JASMINE矩阵进行算法匹配的逐列变换后，分别运行PC（Peter-Clark）、GES（Greedy Equivalence Search）、FCI（Fast Causal Inference）、DirectLiNGAM（Direct Linear Non-Gaussian Acyclic Model）和GRaSP（Greedy Relaxation of the Spirtes/Meek constraints）五种算法，以覆盖不同的假设（如线性、非高斯、隐变量等）。
  3. **方向保持的Bootstrap聚合**：对Bootstrap样本重复运行上述算法，通过加权两阶段共识（weighted two-phase consensus）聚合结果，并保留边的方向信息。
  4. **联合因果推断（JCI）**：通过引入上下文指标（context indicators），将来自不同患者队列（如正常、COVID-19、肿瘤）的数据原则性地合并，消除队列异质性导致的偏差。
  5. **方向审核**：使用残差独立性（RESIT）方法对最终边的方向进行确认性审核。
- **超参数扫描**：整个流水线在系统的 3×3×3 超参数空间（共27种组合）下进行评估。

### 3. 实验设计：数据集、基准与对比方法

- **数据集**：一个包含611名患者的多表型肺图谱，覆盖正常组织、COVID-19肺炎和肺癌三种表型。
- **实验配置**：
  - **跨队列联合因果推断**：将患者按正常、COVID-19、肿瘤背景分层后通过JCI合并构建联合图。
  - **单队列通用跨表型图**：对所有611名患者（不分层）运行单队列因果推断，得到跨表型程序网络。
  - **疾病扩展合并队列**：将COVID-19和癌症扩展的程序集应用于所有患者，但使用单队列因果推断（不进行患者分层）。
- **基准（Ground Truth）**：
  - 可评估的精选边：8条已知/公认的真实关系边。
  - 三个独立精选的禁止方向（forbidden orientations），用于评估方向准确性。
- **对比方法**：未与外部工具对比，而是进行了全面的自身消融实验，包括早期零插补基线配置（zero-imputation baseline）在相同超参数扫描下的比较。

### 4. 资源与算力

- **文中未明确说明**：论文中没有提及所使用的GPU型号、数量、训练时长或任何计算资源信息。仅能推测为一般性服务器/集群环境。

### 5. 实验数量与充分性

- **实验组数**：
  - 涵盖了7种队列/合并配置（跨队列、单队列、疾病扩展合并等）。
  - 27种超参数设置（3×3×3）。
  - 3种共识类型（加权两阶段共识中的不同变体）。
  - 外加敏感性分析（零插补基线对比）。
- **充分性评价**：实验设计系统、消融全面，在同一超参数网格下对比，结论可信。但**仅依赖一个数据集（肺图谱）**，虽然具有611名患者规模，但缺乏外推至其他组织或物种的验证。基准边数量少（8条），可能不足以全面评估方向准确率。

### 6. 论文的主要结论与发现

- **跨队列联合因果推断**（患者分层后JCI）是唯一在三个帕累托最优角（100%边召回、75.0%方向准确率、零禁止方向违反）同时达到最优的配置。
- **单队列通用跨表型图**（低百分位数插补）达到100%已评估召回、62.5%方向准确率、零禁止违反，显著优于零插补基线（各项指标均提升）。
- **疾病扩展合并队列**（不进行患者分层）虽然骨架召回率尚可（35.0%-55.2%），但在方向推断上发生结构性崩溃：方向准确率降至14.3%，禁止方向违反率达60%，表明对异质群体进行简单平均导致方向误判。
- **患者分层+JCI能够消除这种方向崩溃**，且不改变底层算法。

### 7. 优点

- **模块化设计**：允许灵活替换因果发现算法、插补策略等，便于扩展和定制。
- **多算法互补**：同时使用五种性质不同的因果发现算法，覆盖线性/非线性、高斯/非高斯、有无隐变量等场景，提升鲁棒性。
- **方向保序的Bootstrap聚合**：通过保持方向的两阶段共识，避免传统Bootstrap聚合丢失方向信息。
- **系统性超参数扫描**：在统一网格下评估所有配置，确保结论的客观性和可复现性。
- **对异质性的处理**：通过JCI上下文指标实现患者队列的原则性合并，有效解决了异质群体内的方向崩溃问题。

### 8. 不足与局限

- **验证规模有限**：仅在一个肺图谱数据集上验证，且真实边基准仅有8条，导致召回和方向准确率的统计稳定性存疑。
- **方向准确率仍不够高**：最佳配置（75%）表明仍有25%的方向错误，限制了直接生物学推断的可靠性。
- **未提供计算资源信息**：无法评估方法的实际可扩展性或运行成本。
- **观察数据固有局限**：所有结果均为假设生成性质，必须通过实验验证因果关系。
- **未与现有方法（如NicheNet、CellChat等）进行对比**：消融实验仅在自身基线对比，缺乏与领域内主流工具的公平比较，削弱了方法相对优越性的说服力。
- **超参数敏感性未深入讨论**：虽然进行了扫描，但未提供最优超参数的选择依据或在不同数据上的鲁棒性分析。

（完）
