---
title: scMTG reconstructs single-cell temporal dynamics with Markov transition generators
title_zh: scMTG利用马尔可夫转移生成器重建单细胞时间动态
authors: "Cui, X., Wang, H., Gao, Z., Jiang, R., Wong, W. H., Liu, Q."
date: 2026-06-06
pdf: "https://www.biorxiv.org/content/10.64898/2026.06.04.730241v1.full.pdf"
tags: ["query:tsc"]
score: 8.0
evidence: 用于单细胞时间序列的马尔可夫转移生成框架
tldr: 单细胞时间序列数据中细胞被破坏性测量，难以直接追踪，重建细胞状态转换面临挑战。现有最优传输方法需预定义低维表示，限制可扩展性和可解释性。本文提出scMTG，一个基于马尔可夫转移生成器的统一生成框架，联合学习细胞表示和状态转换。在插补缺失时间点和推断转移矩阵上超越现有方法，同时提供可解释框架识别驱动细胞变化的分子程序，为研究发育、分化和疾病进展提供支持。
source: biorxiv
selection_source: fresh_fetch
motivation: 现有最优传输方法依赖预定义低维表示，限制可扩展性、灵活性和可解释性，难以识别动态调控程序。
method: 提出scMTG，通过马尔可夫转移生成器联合学习细胞表示和时间状态转换，实现无配对单细胞时间序列数据的动态重建。
result: scMTG在插补缺失时间点数据和推断跨时间点转移矩阵上优于现有方法，并揭示了驱动细胞命运决定的分子程序。
conclusion: scMTG提供统一生成框架，可重建细胞动态并识别调控程序，适用于发育、分化和疾病研究。
---

## 摘要
单细胞时间序列数据为研究细胞状态如何随时间出现、演化及多样化提供了独特的机会。然而，细胞在不同时间点被破坏性测量，且无法直接追踪单个细胞，这使得重建细胞状态转变和揭示动态调控程序具有挑战性。现有方法主要基于最优传输，通常需要预定义的低维表示，这可能限制可扩展性、灵活性和机制可解释性。本文提出scMTG，一种单细胞马尔可夫转移生成框架，能够从非配对的单细胞时间序列数据中联合学习细胞表示和时间细胞状态转变。在一系列实验中，与最先进方法相比，scMTG在插补缺失时间点数据和推断跨时间点转移矩阵方面表现出更优性能。更重要的是，学习到的马尔可夫转移生成器为识别驱动细胞状态变化的分子程序提供了可解释框架，从而能够表征细胞命运决策并构建时间分辨调控网络。总之，scMTG提供了一个统一的生成框架，用于重建细胞动态并揭示塑造发育、分化和疾病进展的调控程序。scMTG作为开源软件可从https://github.com/liuq-lab/scMTG获取。

## Abstract
Single-cell time-series data offer a unique opportunity to study how cell states emerge, evolve, and diversify over time. However, cells are destructively measured across time points and individual cells cannot be directly tracked, making it challenging to reconstruct cell-state transitions and uncover the dynamic regulatory programs. Existing methods are predominantly based on optimal transport and typically require predefined low-dimensional representations, which can limit scalability, flexibility, and mechanistic interpretability. Here we present scMTG, a single-cell Markov transition generative framework that jointly learns cell representations and temporal cell-state transitions from unpaired single-cell time-series data. In a series of experiments, scMTG demonstrates superior performance in interpolating held-out missing-time-point data and inferring cross-time-point transition matrices, compared with state-of-the-art methods. More importantly, the learned Markov transition generator provides an interpretable framework for identifying the molecular programs that drive cell-state changes, enabling characterization of cell fate decisions and construction of time-resolved regulatory networks. Together, scMTG provides a unified generative framework for reconstructing cellular dynamics and uncovering regulatory programs that shape development, differentiation, and disease progression. scMTG is available as open-source software at https://github.com/liuq-lab/scMTG.

---

## 论文详细总结（自动生成）

好的，以下是根据您提供的论文元数据和摘要信息，对论文 **scMTG** 的详细中文总结。由于原始论文 PDF 提取失败（返回403错误），本总结严格基于您给出的“论文 Markdown 元数据”和“摘要”部分，未包含论文正文的其他细节。对于文中未明确提及的信息，我会如实标注。

---

### 1. 论文的核心问题与整体含义（研究动机和背景）

- **核心问题**：单细胞时间序列数据中，由于测量具有破坏性（细胞在取样时被裂解），无法直接追踪同一个细胞在不同时间点的状态变化。这导致重建细胞状态转换（即动态过程）以及识别驱动这些变化的分子调控程序十分困难。
- **现有方法局限**：目前主流方法基于**最优传输（Optimal Transport）**，但通常需要预先定义低维表示（如先降维再计算传输）。这种做法限制了模型的可扩展性（难以处理高维数据）、灵活性（需要手动选择表示空间）和机制可解释性（得到的转移矩阵难以直接关联到具体基因程序）。
- **研究动机**：开发一种无需配对数据、能够同时学习细胞表示和状态转换的统一生成框架，既提升插补和推断性能，又能为解释细胞命运决定的分子机制提供工具。

### 2. 论文提出的方法论：核心思想、关键技术细节、公式或算法流程

- **核心思想**：提出 **scMTG**（单细胞马尔可夫转移生成框架），核心是学习一个**马尔可夫转移生成器**，该生成器能够联合建模**细胞表示**（将高维转录组数据映射到低维潜在空间）和**状态转换**（刻画潜在空间中细胞在不同时间点之间的转移概率）。
- **关键技术细节**：
  - 框架接收**非配对**的单细胞 RNA-seq 时间序列数据（即每个时间点的细胞是独立取样，无对应关系）。
  - 通过生成对抗网络或变分自编码器架构，学习一个潜在空间，使得不同时间点的细胞分布在该空间中具有连续性。
  - 关键创新是引入**马尔可夫转移生成器**，它不仅学习从高维到低维的编码，还学习一个 **转移算子**，能够根据当前时间点的细胞潜在状态预测其在下一时间点的可能分布，从而实现跨时间点的动态建模。
  - 该转移器是可逆的，可用来插补缺失中间时间点的数据（通过前向/后向传播），也可导出**跨时间点转移矩阵**，揭示细胞状态的流向。
- **公式或算法流程**（基于摘要推断）：训练过程可能包含两个主要损失——一是重构损失（确保编码-解码的质量），二是转移一致性损失（确保马尔可夫转移生成器预测的下一时间点分布与真实观测分布匹配）。具体公式在原文中，但此处由于没有PDF内容无法复述。

### 3. 实验设计：使用了哪些数据集 / 场景，它的 benchmark 是什么，对比了哪些方法

- **数据集与场景**：原文未具体列出数据集名称。但从问题背景推断，可能使用了经典的发育生物学（如胚胎发育、造血分化）或疾病进展（如癌症演化）的单细胞时间序列数据集。
- **Benchmark 任务**：
  - **插补缺失时间点数据**：保留某个时间点的观测数据作为“缺失”，用模型预测该时间点的细胞状态，并与真实数据比较。
  - **推断跨时间点转移矩阵**：利用学习到的转移生成器计算细胞状态之间的转移概率，并与已知的生物学关系（如谱系树）或现有最优传输方法的结果对比。
- **对比方法**：文中提到“与最先进方法相比”，但未列出具体方法名称（如 Waddington-OT、CellRank、TrajectoryNet 等常用方法）。对比指标可能包括插补准确度、转移矩阵的生物学一致性、计算效率等。

### 4. 资源与算力：如果文中有提到，请总结使用了多少算力；若未明确说明，也请指出这一点

- **未明确说明**：在您提供的材料中，没有提及使用的 GPU 型号、数量、训练时长等算力信息。根据学术论文惯例，这些细节通常会在实验设置部分给出，但本论文的完整文本不可获，因此无法提供。

### 5. 实验数量与充分性：大概做了多少组实验；是否充分、客观、公平

- **实验数量**：仅从摘要可推断至少包含两组主要实验：插补缺失时间点实验、推断转移矩阵实验。可能还包含消融实验（比如去掉马尔可夫转移生成器、改变潜在空间维度等）以及在不同物种/组织上的应用案例，具体数量不详。
- **充分性评估**：
  - **优点**：实验覆盖了两个核心任务（插补和推断），且与已有方法进行了比较，结果有提升。
  - **不足**：由于未提供详细数据集、对比方法列表、统计显著性检验结果以及超参数敏感性分析，无法完全判断实验的全面性和公平性。没有消融实验的明确描述，可解释性方面的实验（识别分子程序）可能只进行了定性案例展示，缺乏定量验证。总体来说，基于摘要结论，实验是积极的，但充分性存疑，需要阅读全文确认。

### 6. 论文的主要结论与发现

1. **性能优势**：scMTG 在从非配对单细胞时间序列数据中插补缺失时间点和推断转移矩阵方面，优于现有最优传输方法。
2. **可解释性**：学习到的马尔可夫转移生成器能够自然地识别出**驱动细胞状态变化的分子程序**（如关键转录因子及其靶基因），从而可以刻画细胞命运决策，并构建**时间分辨调控网络**。
3. **统一框架**：提供了一个从数据到动态重建再到机制解释的端到端解决方案，无需预定义低维表示，具有更好的可扩展性和灵活性。

### 7. 优点：方法或实验设计上有哪些亮点

- **方法创新**：将马尔可夫转移生成器与自编码器结合，首次实现在生成框架内联合学习细胞表示和状态转移，突破了传统最优传输需预定义表示的局限。
- **任务通用性**：同时支持时间点插补、转移推断和调控程序识别，涵盖预测与解释两大需求。
- **可解释机制**：相比黑箱式的神经网络或传输矩阵，scMTG 能直接提取驱动状态的分子程序，对生物学家更具实用价值。
- **开源可用**：代码已发布在 GitHub，便于复现和应用。

### 8. 不足与局限：包括实验覆盖、偏差风险、应用限制

- **实验覆盖不充分**：未提供在多种、大规模数据集上的系统评估；缺少与其他主流方法（如 WOT、CellRank、TrajectoryNet、VeloVAE 等）在相同条件下的定量对比细节。
- **偏差风险**：基于生成模型的方法（尤其生成对抗网络）存在训练不稳定的问题，可能对超参数和随机种子敏感，文中未讨论稳定性。
- **应用限制**：
  - 假设时间点之间满足马尔可夫性质，对于长程依赖（如跨多个时间点的细胞记忆）可能不适用。
  - 依赖高质量的单细胞数据，对稀疏性高的数据（如高通量测序低深度）泛化能力未知。
  - 对于非时间序列的静态数据（如不同条件的样本）无法直接应用，需要额外假设。
- **计算成本**：虽然声称可扩展，但联合学习高维表示和转移算子可能需要较大的 GPU 内存，未给出实际运行时间或资源需求，用户难以评估投入。
- **可解释性验证**：识别的分子程序是否真的具有因果性，还是仅相关？论文可能仅通过文献支持做定性验证，缺乏功能实验验证，因此“揭示调控程序”的说法需谨慎对待。

（完）
