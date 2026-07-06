---
title: "Prot2Prop: Structure-informed multitask protein property prediction"
title_zh: Prot2Prop：基于结构信息的蛋白质多任务属性预测
authors: "Gharaie Amirabadi, D., Jackson, C., Kim, D. S., Sprang, M., Amani, K."
date: 2026-06-29
pdf: "https://www.biorxiv.org/content/10.64898/2026.06.28.735009v1.full.pdf"
tags: ["query:fe"]
score: 9.0
evidence: 使用冻结的ProstT5编码器进行多任务蛋白质性质预测
tldr: 蛋白质工程常对可开发性属性使用独立模型，限制效率与任务迁移。本文提出Prot2Prop，基于冷冻ProstT5编码器的多任务框架，通过共享与任务特定适配器联合预测材料产量、溶解度、温度稳定性、聚集倾向、表达产量和折叠稳定性。在测试集上分类AUROC达0.86-0.98，回归Spearman达0.73-0.86，其中温度稳定性AUROC=0.98，聚集倾向Spearman=0.86。校准后折叠稳定性MAE从0.67降至0.48。结果表明参数高效的多任务适应可实现准确统一的蛋白质可开发性预测。
source: biorxiv
selection_source: fresh_fetch
motivation: 现有蛋白质可开发性属性预测模型相互独立，效率低且难以跨任务迁移。
method: 基于冷冻ProstT5编码器，设计共享与任务特定适配器进行多任务学习，联合预测六种蛋白属性。
result: "分类AUROC达0.86-0.98，回归Spearman达0.73-0.86，校准后MAE降低29%。"
conclusion: 参数高效多任务适应能准确统一预测多种蛋白质可开发性属性，提升工程效率。
---

## 摘要
蛋白质工程通常依赖于针对相关可开发性的分离模型，这限制了跨任务的效率和迁移。我们提出了Prot2Prop，这是一个基于冻结的ProstT5编码器的多任务框架，具有共享和任务特定的适配器，用于联合预测六种蛋白质属性：材料产量、溶解度、温度稳定性、聚集倾向、表达产量和折叠稳定性。在保留的测试数据上，Prot2Prop在分类和回归任务上都取得了强劲的性能，包括分类终点的AUROC值在0.86到0.98之间，回归终点的Spearman相关系数在0.73到0.86之间。该模型在温度稳定性（AUROC=0.98）和聚集倾向（Spearman=0.86）方面表现尤为出色。事后校准进一步提高了回归精度，将折叠稳定性的MAE从0.67降低到0.48。这些结果表明，参数高效的多任务适应蛋白质语言模型可以为多种蛋白质可开发性属性提供准确且统一的预测。

## Abstract
Protein engineering often relies on separate models for related developability properties, limiting efficiency and transfer across tasks. We present Prot2Prop, a multitask framework based on a frozen ProstT5 encoder with shared and task-specific adapters for joint prediction of six protein properties: material production, solubility, temperature stability, aggregation propensity, expression yield, and folding stability. Across held-out test data, Prot2Prop achieved strong performance on both classification and regression tasks, including AUROC values ranging from 0.86 to 0.98 for classification endpoints and Spearman correlations ranging from 0.73 to 0.86 for regression endpoints. The model achieved particularly strong performance for temperature stability (AUROC = 0.98) and aggregation propensity (Spearman = 0.86). Post-hoc calibration further improved regression accuracy, reducing folding stability MAE from 0.67 to 0.48. These results demonstrate that parameter-efficient multitask adaptation of protein language models can provide accurate and unified prediction of diverse protein developability properties.



O_FIG O_LINKSMALLFIG WIDTH=200 HEIGHT=132 SRC="FIGDIR/small/735009v1_ufig1.gif" ALT="Figure 1">
View larger version (51K):
org.highwire.dtl.DTLVardef@904e5forg.highwire.dtl.DTLVardef@954cdorg.highwire.dtl.DTLVardef@9e9417org.highwire.dtl.DTLVardef@10c9118_HPS_FORMAT_FIGEXP  M_FIG C_FIG

---

## 论文详细总结（自动生成）

# Prot2Prop：基于结构信息的蛋白质多任务属性预测 详细中文总结

## 1. 核心问题与整体含义（研究动机和背景）
当前蛋白质工程中，可开发性属性（如溶解度、热稳定性、聚集倾向等）通常由各自独立的预测模型分别处理。这种碎片化的建模方式不仅效率低下（需要维护多个模型），而且无法捕捉属性间的生物化学耦合信号（例如，一个提高热稳定性的突变可能同时影响折叠行为和聚集风险）。利用多任务学习共享表征，有望提高参数效率和预测性能。本研究提出了 Prot2Prop，一个基于冻结的 ProstT5 蛋白质语言模型的参数高效多任务框架，用于联合预测六种蛋白质属性，旨在提供一个统一、准确且计算实用的解决方案。

## 2. 方法论
**核心思想**：保持预训练的 ProstT5 编码器冻结，仅训练轻量级的适配模块和任务头，实现跨任务的共享表征与任务特定专化。

**关键技术细节**：
- **输入表示**：蛋白质序列以 `<AA2fold>` 前缀加空格分隔氨基酸的格式 token 化，输入冻结的 ProstT5 编码器生成残基级嵌入。
- **共享残差适配器**：在编码器输出后应用一个共享适配器（LayerNorm → 低维下投影 → GELU → 上投影 → dropout → 残差缩放），学习全局多任务校正。
- **任务特定残差适配器**：每个预测任务都有一个独立的轻量适配器，在共享表征基础上进一步调整 token 级特征，使不同属性关注不同的残基模式。
- **注意力池化**：对每个任务的适配后 token 序列，用一个可学习的小型前馈网络计算注意力权重，生成固定长度的序列表示，而非简单平均。
- **任务头**：分类任务使用较小 MLP，回归任务使用稍大 MLP，输出最终预测。
- **多目标学习策略**：采用掩码标签（masked-label）损失，仅对观测到的标签计算交叉熵（分类）或 MSE（回归）。回归目标用训练集统计标准化。使用逆频率类别加权、任务感知采样权重来平衡数据不平衡。

**算法流程**（文字说明）：
1. 输入蛋白质序列 → 用 AA2fold 格式 token 化 → 输入冻结的 ProstT5 → 得到残基级嵌入。
2. 共享适配器处理残基级嵌入，得到共享表征。
3. 每个任务的任务特定适配器对共享表征进行微调。
4. 每个任务的注意力池化生成序列级表示。
5. 每个任务的任务头输出预测（分类概率或回归值）。
6. 训练时仅对已标注的任务计算损失，反向传播仅更新适配器、池化参数和任务头（共约 3.18M 可训练参数）。

## 3. 实验设计
- **数据集**：六个任务，分为三个分类（material production、solubility、temperature stability）和三个回归（aggregation propensity、expression yield、folding stability）。分类数据来自 AI4Protein 公开数据集，回归数据来自 ProteinGym 的深度突变扫描（DMS）数据集。
- **划分**：80% 训练、10% 验证、10% 测试，基于序列级别划分，确保同一序列不跨集。
- **评测指标**：分类：准确率、平衡准确率、精确率、召回率、F1、AUROC、AUPRC；回归：MAE、RMSE、Spearman 相关系数。
- **对比方法**：
  - 在分类任务上与 NetSolP、SWI、ESM1b-F、BertThermo、ProLaTherm、TemStaPro 进行跨研究比较。
  - 在回归任务（折叠稳定性）上与 SaProt ΔG 和 ESM3 ΔG 进行跨研究比较。
  - 同时与基于 one-hot 编码的线性基线（逻辑回归/岭回归）比较，以显示预训练表征和多任务适配的优势。
- **消融实验**：通过五个版本迭代（2026-04-26 至 2026-05-22）分别测试了：增大任务头容量、添加排序感知回归损失、引入任务特定预池化适配器、学习不确定性权重、加入进化比对监督路径。最终选择验证集最佳种子（Seed 1）作为参考。

## 4. 资源与算力
- **训练**：单张 NVIDIA L40S GPU，10 个 epoch 约需 24 小时。可训练参数约 3.18M。
- **推理**：在 Intel Xeon Gold 6342 CPU 和 NVIDIA A40 GPU 上进行推理时间对比：Prot2Prop 处理 100 条序列（最大长度72）用时 8.95 秒，低于 TemStaPro（15.56 秒）和 SaProt（18.97 秒）。
- **内存**：峰值 CPU RSS 约 4156 MB，峰值 GPU 内存约 4998 MB。
- **框架**：混合精度 CUDA、长度感知批处理、预 token 缓存等加速技术。

## 5. 实验数量与充分性
- **版本迭代**：至少报告了 5 个主要架构版本（2026-04-26, 04-28, 04-29, 04-30, 05-22），每个版本在验证集上评估所有六个任务指标。
- **种子实验**：最终架构使用多个随机种子重训（报告了种子 42、26、1 以及一个四模型集成），共至少 4 组种子结果。
- **校准实验**：对分类任务进行阈值调优，对回归任务进行仿射校准，并展示前后对比。
- **与线性基线对比**：使用 one-hot 编码的 logistic/ridge regression 在验证集上比较。
- **跨研究比较**：与多个外部模型在相同任务上（但数据集、标签定义、评估协议不同）进行上下文对比。
- **充分性评价**：实验设计较为系统，覆盖了核心消融、种子鲁棒性、校准效果和基线对比。但缺乏在完全相同条件下的直接标准基准（如使用相同数据划分重新实现外部方法），也缺乏匹配的单任务模型训练对比（如对同一 backbone 分别训练单任务模型），因此对多任务优势的量化不够严格。总体实验数量可接受，但严格性上存在提升空间。

## 6. 主要结论与发现
- 参数高效的多任务适应（冻结 backbone + 共享/任务特定适配器）可以在统一框架内同时对分类和回归任务达到强预测性能。
- **分类**：AUROC 0.86–0.98（材料生产 0.866、溶解度 0.870、温度稳定性 0.984）。
- **回归**：Spearman 0.73–0.86（聚集倾向 0.861、表达产量 0.732、折叠稳定性 0.838）。
- **关键架构改进**：引入任务特定预池化适配器（2026-04-29）是最有效的单一改变，显著提升了回归性能而不损害分类。
- **校准效果**：事后仿射校准将折叠稳定性 MAE 从 0.677 降至 0.486，说明性能瓶颈部分来自输出标度偏移而非表征质量。
- 与 one-hot 线性基线相比，Prot2Prop 在所有分类任务和回归的 Spearman 上明显更优，但部分回归 MAE/RMSE 提升有限，提示某些属性仍可由线性特征主导。

## 7. 优点
- **参数高效**：仅训练 3.18M 参数（冻结 ProstT5），相比全微调极大降低计算和存储成本。
- **统一建模**：同时处理分类和回归异构标签，便于实际筛选流程。
- **共享与专化结合**：共享适配器捕捉全局模式，任务特定适配器实现精准微调，注意力池化进一步允许任务关注不同残基。
- **计算效率**：推理速度快于对比模型（TemStaPro、SaProt），适合高通量应用。
- **开源与可复现**：代码和权重在 GitHub 公开，并提供在线服务。

## 8. 不足与局限
- **缺乏直接标准基准**：与外部模型的比较是跨研究（cross-study），数据集、标签定义、评估协议不同，不能保证公平对比。缺少在同一工况下重训其他模型的头对头实验。
- **缺少匹配单任务基线**：未在相同 backbone 和数据处理下训练单任务模型，无法精确量化多任务迁移带来的实际增益。
- **任务覆盖有限**：当前六种属性主要围绕可开发性，未包括结合亲和力、酶活性、免疫原性等更复杂或上下文依赖的属性。
- **未探索其他 backbone 或适配方案**：仅使用 ProstT5 作为 backbone，没有系统比较 ESM2、ESM3 或其他语言模型；适配方案仅使用残差适配器，未尝试 LoRA/qLoRA。
- **训练数据规模与标注质量**：数据集来自公开资源，可能存在噪声或不平衡（如部分任务类不平衡显著），但已通过加权处理缓解。未报告数据量级细节。
- **种子变异性**：回归任务在种子间波动较大，表明模型在连续输出上对初始化敏感，鲁棒性有待进一步提升。

（完）
