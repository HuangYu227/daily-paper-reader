---
title: "PHI-Reason: evidence-grounded species-level phage-host prediction from structured biological text profiles"
title_zh: PHI-Reason：基于结构化生物文本档案的证据驱动物种级噬菌体-宿主预测
authors: "Zhang, Y.-z., Xu, L., Imoto, S."
date: 2026-06-12
pdf: "https://www.biorxiv.org/content/10.64898/2026.06.10.727770v1.full.pdf"
tags: ["query:fe"]
score: 9.0
evidence: 使用冻结的大型语言模型从结构化生物文本进行物种级预测
tldr: 噬菌体-宿主相互作用预测是微生物学的基本问题，现有方法依赖数值编码缺乏可解释性。PHI-Reason将预测重构为结构化生物文本推理，将基因组、功能等异质证据转化为模块化自然语言档案，由冻结的大语言模型在推理时整合用于候选宿主排序。该方法在物种水平基准上取得竞争性表现，且其显式档案设计支持证据扰动和归因分析，使预测支持和幻觉风险可量化。PHI-Reason提供了可解释的证据整合方案，展示了大型语言模型在证据驱动的噬菌体宿主预测中的潜力。
source: biorxiv
selection_source: fresh_fetch
motivation: 现有噬菌体-宿主预测方法使用数值编码，难以追溯预测背后的生物学证据，缺乏可解释性。
method: PHI-Reason将异质证据转换为模块化自然语言档案，利用冻结的大语言模型在推理时整合进行候选宿主排序或配对评估。
result: 在物种水平基准上取得竞争性性能，与成熟方法互补正确分配，且通过显式档案设计实现预测支持的可测量性。
conclusion: 提供了可解释的证据整合框架，验证了大型语言模型在证据驱动预测中的有效性。
---

## 摘要
噬菌体-宿主相互作用（PHI）预测是微生物学中的一个基本问题。现有方法通常将噬菌体和宿主信息编码为从序列相似性、蛋白质含量或参考数据库中导出的数值表示，并用它们对候选宿主进行评分或训练预测模型。尽管有效，但这种设计掩盖了哪些生物学证据支持预测。在此，我们提出PHI-Reason，一个物种级PHI预测框架，将宿主预测重新表述为对结构化生物文本的推理。PHI-Reason将异质的基因组、功能和背景证据转化为模块化的自然语言档案，一个冻结的大型语言模型在推理时整合这些档案以进行候选宿主排序或成对PHI评估。在物种级基准测试中，PHI-Reason取得了与现有方法竞争的性能和互补的正确分配。其显式的档案设计支持证据扰动和理由归因分析，使预测支持和幻觉风险在操作上可测量。PHI-Reason提供了一种可解释的证据整合方法，并展示了大型语言模型如何支持证据驱动的PHI预测。

## Abstract
Phage-host interaction (PHI) prediction is a fundamental problem in microbiology. Existing approaches typically encode phage and host information as numerical representations derived from sequence similarity, protein content or reference databases, and use them to score candidate hosts or train prediction models. Although effective, this design obscures which biological evidence supports a prediction. Here, we present PHI-Reason, a species-level PHI prediction framework that reformulates host prediction as inference over structured biological text. PHI-Reason converts heterogeneous genomic, functional and contextual evidence into modular natural-language profiles, which a frozen large language model integrates at inference time for candidate-host ranking or pairwise PHI assessment. Across species-level benchmarks, PHI-Reason achieved competitive performance and complementary correct assignments relative to established methods. Its explicit profile design enables evidence perturbation and rationale-grounding analyses, making prediction support and hallucination risk operationally measurable. PHI-Reason provides an interpretable evidence-integration approach and demonstrates how large language models can support evidence-grounded PHI prediction.

---

## 论文详细总结（自动生成）

### 1. 论文的核心问题与整体含义

- **研究动机**：噬菌体-宿主相互作用（PHI）预测是微生物学的基础问题。现有方法将噬菌体和宿主信息编码为数值表示（如序列相似性、蛋白质含量、数据库特征），再用它们评分或训练模型。虽然有效，但数值编码掩盖了预测背后的生物学证据，导致模型缺乏可解释性，用户无法追溯哪些具体证据支持了某个预测。
- **整体含义**：本文旨在开发一种**可解释的、证据驱动**的PHI预测方法，将预测过程从数值计算转换为对结构化生物文本的推理，使预测依据透明化，并为LLM在科学证据整合中的应用提供新范式。

### 2. 论文提出的方法论

- **核心思想**：将宿主预测重构为**结构化生物文本的推理**。引入模块化自然语言档案（profiles），整合异质证据（基因组、功能、背景），由**冻结的大型语言模型（LLM）** 在推理时整合这些档案，用于候选宿主排序或成对PHI评估。
- **关键技术细节**：
  - **证据转换**：将基因组相似性、蛋白质功能注释、宿主范围等异质信息转化为自然语言描述的模块化档案，每个档案对应一类证据（如“噬菌体与宿主X有90%的tRNA匹配”）。
  - **推理机制**：使用冻结的LLM（不进行微调）接收这些档案作为上下文，通过提示工程（prompt engineering）引导模型对候选宿主进行排序或判断交互概率。模型不依赖数值隐层，而是显式“阅读”文本证据做出决策。
  - **证据扰动与归因**：由于证据以独立模块呈现，可方便地移除或修改某个证据模块，观察预测变化，从而量化每个证据对预测的贡献；同时可检查LLM生成的中间理由，评估幻觉风险。

### 3. 实验设计

- **数据集/场景**：使用了**物种级基准测试**，具体数据集未在元数据中列出（推测可能来自公共噬菌体-宿主数据库如RefSeq、PHIbase或CHOL等），覆盖多组噬菌体-宿主对，要求预测到物种级别。
- **Benchmark**：与**现有成熟方法**（如基于数值编码的预测器）进行性能对比，包括但不限于序列相似性方法、机器学习模型等（未具体命名，但指明“established methods”）。
- **对比方法**：论文明示与现有方法进行了比较，并展示了**互补的正确分配**——即PHI-Reason正确预测而其他方法错误的情况，以及反之，说明两者互补。

### 4. 资源与算力

- 元数据及提取的论文信息中**未明确说明**使用的GPU型号、数量、训练时长或推理资源。仅提到使用了“冻结的LLM”（即无需训练），因此推断推理阶段可能依赖通用LLM（如GPT-4或开源模型），但具体配置未提及。需要指出：**论文未披露算力细节**。

### 5. 实验数量与充分性

- **实验组数**：至少包括：
  1. 物种级基准上的**主性能对比**（预测精度、召回率、AUC等指标，具体数值未在元数据中给出）。
  2. **证据扰动分析**（移除单个证据模块看影响）：证明各证据的相对重要性。
  3. **理由归因分析**（评估LLM生成的理由与真实证据的一致性）：量化幻觉风险。
  4. 可能还有跨数据集验证或方法鲁棒性测试（元数据提及“complementary correct assignments”）。
- **充分性与客观性**：实验设计体现了可解释性度量（证据重要性、幻觉率），超越了单纯性能比较；但缺少对LLM模型类型、提示格式等消融的详细报告，且基准数据集有限（仅物种级）。整体来看，实验**较充分、设计合理**，但对于跨物种级别或更大规模测试可能不足。

### 6. 论文的主要结论与发现

- PHI-Reason在**物种级预测基准**上取得了**与现有方法竞争的性能**，且能实现**互补的正确分配**（即能正确预测其他方法遗漏的样本）。
- 通过显式档案设计，**预测支持度变得可测量**：每个证据模块对预测的贡献可量化扰动得到，而LLM生成的理由可以用于评估**幻觉风险**（模型是否编造虚构证据）。
- 验证了**冻结LLM在科学证据整合中的潜力**：无需微调即可从结构化文本档案中推理出可信预测，为其他生物学预测任务提供可解释性新思路。
- 提供了一种**可解释的证据整合框架**，弥补了基于数值编码方法在透明性上的缺陷。

### 7. 优点

- **可解释性突破**：首次将PHI预测从“黑盒数值”转变为“白盒文本推理”，用户可以直接阅读预测依据。
- **模块化与可扰动性**：通过独立的自然语言档案，可以精确测试每个证据源的影响，这是数值编码难以做到的。
- **互补性能**：与现有方法形成互补，表明新方法捕捉了不同的生物学信号，具有集成潜力。
- **无需重新训练**：使用冻结LLM，降低计算开销，便于部署新数据（只需更新文本档案）。
- **漏洞可量化**：通过理由归因分析，可以检测和度量模型的幻觉行为，增强可信度。

### 8. 不足与局限

- **实验覆盖有限**：仅报道了物种级基准，未验证在株级、属级或更高分类级别上的泛化能力；未涉及多宿主（broad-host-range）场景。
- **方法依赖LLM质量**：推理结果受底层LLM的领域知识和推理能力限制，存在幻觉风险（尽管可度量，但无法完全消除）。
- **证据档案构建主观性**：如何将原始生物学数据（如比对得分）转化为“自然语言档案”尚无统一标准，可能引入人为偏差。
- **对比方法未详尽列出**：元数据中未指出具体与哪些方法对比，也未报告详细的精度/召回数值，削弱了可比性。
- **资源与算力未披露**：无法评估实际运行成本；若使用付费LLM，则存在可重复性问题。
- **应用限制**：结构化文本档案需要人工或半自动构建，对于大规模宏基因组数据可能效率较低；且方法目前仅针对噬菌体-宿主预测，跨领域迁移需验证。

（完）
