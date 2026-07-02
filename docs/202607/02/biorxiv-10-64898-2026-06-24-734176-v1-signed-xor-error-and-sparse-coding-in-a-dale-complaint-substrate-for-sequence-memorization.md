---
title: Signed-XOR Error and Sparse Coding in a Dale-Complaint Substrate for Sequence Memorization
title_zh: 在符合达勒法则的基底上的有符号XOR误差与稀疏编码用于序列记忆
authors: "Pena Fernandez, M., Lloret Iglesias, L., Marco de Lucas, J."
date: 2026-06-29
pdf: "https://www.biorxiv.org/content/10.64898/2026.06.24.734176v1.full.pdf"
tags: ["query:fe"]
score: 7.0
evidence: 冻结的稀疏随机投影编码器
tldr: 在生物可塑性约束下，探索网络记忆离散序列所需的最小机制。采用Dale定律（兴奋/抑制分离、非负权重）和稀疏随机投影编码，结合signed-XOR误差与k-WTA稀疏编码，在50个单音旋律基准上实现完美存储与自回归回忆。实验表明，容量决定最终保真度，音乐结构无额外增益，得到Dale兼容、无梯度的稀疏联想记忆。
source: biorxiv
selection_source: fresh_fetch
motivation: 探究在Dale定律约束下，网络记忆离散序列所需的最小机制。
method: 遵循Dale定律，使用signed-XOR误差和稀疏k-WTA编码存储旋律。
result: "L=512时100%召回训练旋律并区分新旋律；消融证实signed误差、E/I路由等关键。"
conclusion: 得到Dale兼容、无梯度的稀疏联想记忆，容量决定保真度。
---

## 摘要
当网络受限于生物学上合理的基底时，需要多少机制来记忆和回忆离散序列？我们使用50个短的单声部4/4旋律作为受控的序列记忆基准来探讨这个问题。每个节拍用两个干净的独热种群编码——一个12维音高码和一个独立的2维{起始,持续}码——解码器输出相同的14维码，因此自回归循环以单一神经格式闭合。模型遵循达勒法则：潜在单元是兴奋性或抑制性的，突触权重非负，解码器实现为显式的多接触束，编码器是冻结的稀疏随机投影，布线密度为皮层密度（约10%）。在该基底上，局部的ENGRAMMER有符号XOR读取规则结合稀疏的k-赢者通吃编码精确存储训练语料库。通过适度的潜在扩展（L=512），模型达到100%的教师强制和自回归音高准确率，识别所有训练旋律，并将所有保留的旋律作为新颖的区分，重叠为零。消融实验表明，有符号误差、稀疏编码、显式的E/I路由和多接触突触是主要的承载成分，而学习编码器则强烈有害，密集输入布线没有帮助。容量扫描显示，达勒法则主要增加了稳定自回归回忆所需的容量：教师强制存储在L=128到L=256之间饱和，而自由运行回忆在L=512时达到完美。匹配的随机语料库达到相同的最终保真度，并且每个容量下的回忆至少同样好，表明音乐结构在此基准上不改善回忆，最终保真度由容量而非结构决定。结果是一个符合达勒法则、无梯度的稀疏关联记忆，而非通用的序列学习器。

## Abstract
How much machinery does a network need to memorize and recall discrete sequences when constrained to a biologically plausible substrate? We address this question using 50 short monophonic melodies in 4/4, used only as a controlled sequence-memory benchmark. Each beat is encoded with two clean one-hot populations - a 12-way pitch code and a separate 2-way {onset, sustain} code - and the decoder emits the same 14-dimensional code, so the autoregressive loop closes in a single neural format. The model obeys Dales law: latent units are excitatory or inhibitory, synaptic weights are non-negative, the decoder is implemented as explicit multi-contact bundles, and the encoder is a frozen sparse random projection wired at cortical ([~]10%) density. On this substrate, a local ENGRAMMER signed-XOR read-out rule combined with a sparse k-winner-take-all code stores the training corpus exactly. With a modest latent expansion (L = 512), the model reaches 100% teacher-forced and autoregressive pitch accuracy, recognizes all training melodies, and separates all held-out melodies as novel with zero overlap. Ablations show that the signed error, sparse code, explicit E/I routing, and multi-contact synapses are the main load-bearing ingredients, whereas learning the encoder is strongly detrimental and dense input wiring does not help. Capacity sweeps show that Dales law mainly increases the capacity required for stable autoregressive recall: teacher-forced storage saturates between L = 128 and L = 256, while free-running recall becomes perfect by L = 512. A matched random corpus reaches the same final fidelity and is recalled at least as well at every capacity, indicating that musical structure does not improve recall on this benchmark and that final fidelity is set by capacity rather than by structure. The result is a Dale-compliant, gradient-free sparse associative memory rather than a general sequence learner.