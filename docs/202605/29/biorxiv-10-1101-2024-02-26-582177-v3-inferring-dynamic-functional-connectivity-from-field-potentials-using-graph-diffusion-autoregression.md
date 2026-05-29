---
title: Inferring Dynamic Functional Connectivity from Field Potentials Using Graph Diffusion Autoregression
title_zh: 基于图扩散自回归从场电位推断动态功能连接
authors: "Schwock, F., Bloch, J., Khateeb, K., Zhou, J., Atlas, L., Yazdan-Shahmorad, A."
date: 2026-05-29
pdf: "https://www.biorxiv.org/content/10.1101/2024.02.26.582177v3.full.pdf"
tags: ["query:tsc"]
score: 7.0
evidence: 从场电位信号推断动态功能连接，使用自回归模型
tldr: 传统功能连接估计多局限于静态分析，且未利用大脑结构组织信息，无法反映神经活动的动态变化。本文提出图扩散自回归模型（GDAR），基于预定义结构连接图，通过线性自回归过程在边上生成动态功能连接信号，并引入扩散约束提升性能。在模拟数据及猕猴皮层记录实验中，GDAR成功捕捉了光遗传刺激诱发的快速通信动态、中风后静息态连接变化以及执行任务时的行为相关神经活动。该模型为动态功能连接推断提供了结构约束下的新框架，具有重要应用价值。
source: biorxiv
selection_source: fresh_fetch
motivation: 现有功能连接估计为静态且忽略结构信息，无法捕捉神经活动动态。
method: 在结构连接图上构建线性自回归模型，并加入扩散约束，形成GDAR模型。
result: 在模拟和猕猴真实数据上验证，能描述快速通信动态、中风后变化及行为关联。
conclusion: GDAR模型整合结构信息，有效推断动态功能连接，促进神经动态研究。
---

## 摘要
随着多部位神经记录技术的快速发展和更好地理解认知过程的努力，估计动态功能连接（dFC）正引起越来越多的关注。然而，大多数研究集中于功能连接的静态估计，无法捕捉高度动态的神经过程，同时也忽略了大脑结构组织信息。为了解决这些问题，我们引入了一类网络约束的线性自回归模型，该模型在预定义的结构连接图的边上生成高度动态的功能连接信号。此外，我们证明添加额外的扩散约束可以提高模型的性能。我们成功地在模拟神经活动以及置于猕猴感觉运动皮层的硬膜下和皮层内微电极阵列记录上验证了所得到的图扩散自回归（GDAR）模型，展示了其描述光遗传刺激诱导的快速通信动态、中风后和电刺激后静息态dFC的变化以及伸手任务期间行为的神经关联的能力。

## Abstract
Estimating dynamic functional connectivity (dFC) is attracting increased attention, spurred by rapid advancements in multi-site neural recording technologies and efforts to better understand cognitive processes. Yet, most studies focus on static estimates of functional connectivity that cannot capture highly dynamic neural processes, while also ignoring information about the structural organization of the brain. To address these issues, we introduce a class of network-constrained linear autoregressive models that give rise to a highly dynamic functional connectivity signal on the edges of a predefined structural connectivity graph. Furthermore, we demonstrate that adding an additional diffusion constraint improves the model's performance. We successfully validated the resulting graph diffusion autoregressive (GDAR) model on simulated neural activity and recordings from subdural and intracortical micro-electrode arrays placed in macaque sensorimotor cortex demonstrating its ability to describe rapid communication dynamics induced by optogenetic stimulation, changes in resting state dFC following stroke and electrical stimulation, and neural correlates of behavior during a reach task.