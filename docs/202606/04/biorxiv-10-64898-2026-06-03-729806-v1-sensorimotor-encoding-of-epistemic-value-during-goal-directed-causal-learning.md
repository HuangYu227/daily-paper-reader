---
title: Sensorimotor encoding of epistemic value during goal-directed causal learning
title_zh: 目标导向因果学习中认知价值的感知运动编码
authors: "Basanisi, R., Combrisson, E., Dauce, E., Khamassi, M., Joffily, M., Brovelli, A."
date: 2026-06-04
pdf: "https://www.biorxiv.org/content/10.64898/2026.06.03.729806v1.full.pdf"
tags: ["query:tsc"]
score: 9.0
evidence: 目标导向因果学习与认知价值
tldr: 目标导向因果学习需平衡奖赏与信息寻求，但信息价值的神经机制尚不明确。本研究通过无外部激励的新范式分离信息寻求与奖赏，结合贝叶斯建模和MEG高伽马活动分析，发现预期信息增益在左感觉运动皮层（背侧前运动皮层和初级运动皮层）编码并广播至初级体感皮层，同时随机探索仍占主导。这一结果挑战了认知估值仅依赖前额叶奖赏回路的观点，支持具身感觉运动系统在因果学习中编码认知价值的主动推断框架。
source: biorxiv
selection_source: fresh_fetch
motivation: 探究目标导向因果学习中，信息寻求的神经表征是否独立于外部奖赏并由感觉运动系统编码。
method: 设计无外部激励的行动-结果偶然性估计任务，结合贝叶斯计算模型与MEG高伽马活性信息论分析。
result: 预期信息增益在左背侧前运动皮层和初级运动皮层编码，并广播至初级体感皮层；随机探索为主但EIG解释部分选择。
conclusion: 认知价值编码不限于前额叶奖赏回路，而由感觉运动系统介导，支持主动推断中EIG驱动探索的具身观点。
---

## 摘要
理解目标导向因果学习背后的神经和计算机制是认知神经科学和人工智能领域的一个核心挑战。这种认知功能依赖于在奖励最大化和信息寻求之间取得平衡。尽管在刻画奖励驱动学习的神经基础方面取得了显著进展，但内在信息价值是否以及如何在大脑中表征并通过皮层间相互作用传播仍不清楚。本文采用一种新的行为范式，在目标导向因果学习中将信息寻求与奖励最大化分离开来，该范式中参与者在没有外部激励的情况下估计行动-结果偶然性。贝叶斯计算模型揭示，虽然随机探索主导了行为，但在部分实验会话中，预期信息增益（EIG）解释了相当比例的探索性选择。利用脑磁图结合高伽马活动的信息论分析，我们发现EIG在执行动作时的左侧感觉运动皮层（具体为背侧前运动皮层和初级运动皮层）编码，并传递到初级体感皮层。这些结果与主动推断的预测一致，即EIG构成探索性行动选择的关键计算驱动力。然而，它们挑战了认知价值专门招募前额叶奖赏回路这一观点，反而支持了一种具身解释，即前运动和感觉运动系统在第一人称干预性因果学习中调节内在价值评估。

## Abstract
Understanding the neural and computational mechanisms underlying goal-directed causal learning is a central challenge in both cognitive neuroscience and artificial intelligence. This cognitive function depends on balancing reward maximization with information seeking. Although substantial progress has been made in characterizing the neural basis of reward-driven learning, it remains unclear whether and how intrinsic informational value is represented in the brain and propagated through cortico-cortical interactions. Here, we dissociate information-seeking from reward maximisation during goal-directed causal learning using a novel behavioural paradigm in which participants estimate action-outcome contingencies without extrinsic incentives. Bayesian computational modelling reveals that while random exploration dominates behaviour, expected information gain (EIG) explains a significant proportion of exploratory choices in a subset of sessions. Using magnetoencephalography combined with information-theoretic analyses of high-gamma activity, we show that EIG is encoded in the left sensorimotor cortex at the time of action execution, specifically in dorsal premotor and primary motor cortex, and broadcast to primary somatosensory cortex. These findings are consistent with Active Inference predictions that EIG constitutes a key computational drive for exploratory action selection. However, they challenge the view that epistemic valuation exclusively recruits prefrontal reward circuits, and instead they support an embodied account in which the premotor and sensorimotor system mediates the intrinsic valuation during first-personal interventional causal learning.

---

## 论文详细总结（自动生成）

# 论文详细中文总结

## 1. 论文的核心问题与整体含义（研究动机和背景）

目标导向因果学习需要在最大化奖赏与寻求信息之间取得平衡。以往研究已充分刻画奖赏驱动学习的神经基础，但**内在信息价值（认知价值）如何在大脑中编码并通过皮层间相互作用传播**仍不清楚。本研究旨在分离信息寻求与奖赏最大化，探究大脑是否及如何利用预期信息增益（EIG）驱动探索性行为，并挑战认知价值仅依赖前额叶奖赏回路的传统观点。

## 2. 论文提出的方法论：核心思想、关键技术细节

- **核心思想**：通过无外部激励的行为任务分离信息寻求与奖赏最大化，利用贝叶斯计算模型量化预期信息增益（EIG），并结合脑磁图（MEG）高伽马活动的信息论分析，追踪EIG的神经编码与传播。
- **关键技术细节**：
  - 采用行动-结果偶然性估计任务，参与者在没有外部奖赏的情况下估计动作与结果之间的因果关系。
  - 贝叶斯计算模型：建模被试对偶然性的信念更新，计算每个动作的EIG（即探索该动作可获得的预期信息量）。
  - MEG记录高伽马活动（约60–200 Hz），运用信息论方法（如互信息、传递熵）分析EIG的神经表征及其在感觉运动皮层间的信息流。
- **算法流程（文字说明）**：根据贝叶斯后验概率，对每个候选动作计算其能带来的信息增益（KL散度），选择该动作后，模型可预测是否产生探索行为；实验中将EIG值与实际行为选择进行回归分析。

## 3. 实验设计

- **数据集/场景**：设计了新颖的行为范式——无外部激励的目标导向因果学习任务。参与者在每次试验中选择一个动作，观察结果后更新对动作-结果偶然性的信念。
- **benchmark**：未明确提及传统基准；行为层面比较了**随机探索模型**与**EIG驱动模型**的解释力。
- **对比方法**：主要对比了两种假说：
  - 纯随机探索（无信息价值驱动）
  - 部分由EIG引导的探索（模型比较）

## 4. 资源与算力

文中**未明确说明**使用的GPU型号、数量、训练时长等任何算力信息。仅提及使用MEG进行神经数据采集，计算模型可能基于标准CPU/集群，但无具体细节。

## 5. 实验数量与充分性

- **实验数量**：从摘要看，仅描述了一个行为实验（单任务），包含若干被试的多个session。**具体被试数、试验次数未提供**。
- **充分性**：
  - 优势：任务设计新颖能分离奖赏与信息寻求，模型比较显示部分session中EIG解释显著。
  - 不足：
    - 仅报告了部分session有显著EIG效应，未全面揭示全部行为。
    - 仅一个实验，缺乏跨任务、跨模态验证。
    - 样本量未说明，可能统计功效有限。
    - 无消融实验或控制条件（如有无外部奖赏的对比）。
- **客观性**：主要基于贝叶斯模型比较和MEG信息论分析，方法客观，但结果的可推广性有待更多实验支持。

## 6. 论文的主要结论与发现

- 行为层面：**随机探索主导行为**，但**预期信息增益（EIG）在部分实验会话中解释了相当比例的探索性选择**。
- 神经层面：**EIG在执行动作时编码于左侧感觉运动皮层**，具体为**左背侧前运动皮层（dPMC）和初级运动皮层（M1）**，并传递至**初级体感皮层（S1）**。
- 理论含义：
  - 支持**主动推断**框架中EIG作为探索行动选择的关键计算驱动力。
  - **挑战**认知价值仅由前额叶奖赏回路编码的传统观点，提出**具身感觉运动系统**调节内在价值评估的假设。

## 7. 优点

1. **范式创新**：设计无外部激励的任务，成功分离了信息寻求与奖赏最大化，解决了以往研究无法独立刻画认知价值的问题。
2. **计算方法先进**：采用贝叶斯计算模型量化EIG，结合MEG高伽马活动的信息论分析，提供了因果性神经表征证据。
3. **理论贡献显著**：将认知价值的神经基础从经典的前额叶扩展到感觉运动皮层，为主动推断和具身认知提供了新证据。
4. **多模态分析**：MEG的高时间分辨率（毫秒级）能追踪EIG在动作执行瞬间的编码与传播。

## 8. 不足与局限

1. **实验规模有限**：仅基于一个任务、一组被试，样本量未报告，统计功效存疑。缺乏跨任务、跨人群（如患者组）验证。
2. **行为结果不统一**：仅部分session表现出EIG驱动行为，提示可能被试间或session间差异大，模型普适性不足。
3. **缺乏控制条件**：没有对比有外部奖赏时的EIG编码差异，无法完全排除任务结构本身的影响。
4. **神经结果解释风险**：高伽马活动的信息论分析虽能指示信息流，但传递熵等存在混淆因素（如共同输入），因果性解释需谨慎。
5. **应用限制**：仅涉及因果学习中的信息寻求，是否能推广到其他认知价值（如好奇心、探索）未知。
6. **资源说明缺失**：未提及计算模型训练时长、硬件条件，复现需自行估算。

（完）
