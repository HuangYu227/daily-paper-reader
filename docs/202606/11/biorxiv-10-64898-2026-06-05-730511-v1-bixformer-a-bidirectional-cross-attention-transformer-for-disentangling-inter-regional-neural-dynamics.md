---
title: "BiXformer: A Bidirectional Cross Attention Transformer for Disentangling Inter-Regional Neural Dynamics"
title_zh: "BiXformer: 用于解缠区域间神经动力学的双向交叉注意力Transformer"
authors: "El Sayed, O., Han, Y., Dragoi, T., Economo, M. N., DePasquale, B."
date: 2026-06-10
pdf: "https://www.biorxiv.org/content/10.64898/2026.06.05.730511v1.full.pdf"
tags: ["query:tsc"]
score: 7.0
evidence: 使用掩码注意力在神经时间序列中分离因果与非因果流
tldr: 高吞吐量神经记录产生多脑区数据，但双向、时延的区间通信使解读困难。BiXformer通过定向掩码注意力将通信分解为因果与非因果流，无需线性或平稳性假设。在合成数据上准确恢复延迟和潜在结构，应用于运动任务多脑区记录，解析出与感觉反馈和运动信号共存的时序成分。该模型为揭示复杂神经回路中动态定向通信提供灵活框架。
source: biorxiv
selection_source: fresh_fetch
motivation: 多脑区神经记录中双向通信与时间延迟难以分离，现有方法依赖线性假设，亟需无模型的分解方法。
method: BiXformer采用双向交叉注意力变压器，通过方向性掩码注意力分离因果和反因果流，并估计通信延迟。
result: 合成数据上准确恢复已知延迟和潜在动态；实际运动任务数据中识别出与感觉反馈和运动相关的可解释成分。
conclusion: BiXformer灵活揭示复杂神经回路中动态定向通信，适用于多种多脑区数据分析。
---

## 摘要
高通量神经记录技术的进步使得能够同时测量行为动物多个脑区的活动，产生了规模和丰富度空前的数据集。由于区域间通信的双向性和时间偏移特性，前馈和反馈信号在神经群体中叠加，解释这些数据仍然具有挑战性。我们提出了BiXformer，一种双向交叉注意力Transformer，通过使用定向掩码注意力将区域间通信分解为因果和非因果流，从而解缠这些相互作用。通过在注意力头内强制时间约束，BiXformer恢复了低维的定向潜在动态，并估计了通信延迟，而不依赖于线性或平稳性假设。我们在已知真实延迟的合成数据集上验证了模型，展示了准确恢复潜在结构和区域间时序的能力。应用于同时记录的神经行为数据和运动任务中的多区域神经记录，BiXformer揭示了可解释的、时间结构化的成分，这些成分与感觉反馈和运动相关信号的共存一致。这些结果确立了BiXformer作为揭示复杂神经电路中动态定向通信的灵活框架。

## Abstract
Advances in high-throughput neural recording technologies enable simultaneous measurement of activity across multiple brain regions in behaving animals, producing datasets of unprecedented scale and richness. Interpreting these data remains challenging due to the bidirectional and temporally offset nature of inter-regional communication, where feedforward and feedback signals are superimposed within neural populations. We introduce BiXformer, a bidirectional cross-attention transformer that disentangles these interactions by decomposing inter-regional communication into causal and acausal streams using directionally masked attention. By enforcing temporal constraints within attention heads, BiXformer recovers low-dimensional, directed latent dynamics and estimates communication delays without relying on linearity or stationarity assumptions. We validate the model on synthetic datasets with known ground-truth delays, demonstrating accurate recovery of both latent structure and inter-regional timing. Applied to simultaneous neural-behavioral recordings and multi-region neural recordings during a movement task, BiXformer reveals interpretable, temporally structured components consistent with the coexistence of sensory feedback and motor-related signals. These results establish BiXformer as a flexible framework for uncovering dynamic, directed communication in complex neural circuits.