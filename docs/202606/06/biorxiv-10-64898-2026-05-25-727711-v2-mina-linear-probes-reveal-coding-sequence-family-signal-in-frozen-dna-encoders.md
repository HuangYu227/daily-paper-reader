---
title: "MINA: linear probes reveal coding-sequence family signal in frozen DNA encoders"
title_zh: MINA：线性探针揭示冷冻DNA编码器中的编码序列家族信号
authors: "Wijaya, A. S., Leung, H., Yoo, H."
date: 2026-05-30
pdf: "https://www.biorxiv.org/content/10.64898/2026.05.25.727711v2.full.pdf"
tags: ["query:fe"]
score: 7.0
evidence: 冷冻编码器探测用于DNA序列
tldr: 冷冻DNA编码器作为基因组特征提取器，但其嵌入中哪些信息已线性可及尚不明确。本文提出MINA探针，测试从编码序列和TSS中心窗口恢复蛋白质家族和GenePT描述。结果表明编码序列能较好恢复家族信息（NT-v2达macro-F1 0.828），而TSS窗口性能显著下降，GenePT匹配较弱。研究揭示冷冻编码器主要编码编码序列的家族信号，而非通用基因功能，为解释模型提供了新视角。
source: biorxiv
selection_source: fresh_fetch
motivation: 冷冻DNA编码器的嵌入中哪些信息已线性可及尚不清楚，需要系统探测。
method: 提出MINA基准，对比编码序列和TSS窗口，测试恢复蛋白质家族和GenePT嵌入的能力。
result: 编码序列恢复家族达macro-F1 0.828/kappa 0.821，TSS窗口性能大降，GenePT匹配弱。
conclusion: 冷冻编码器主要编码编码序列的家族信号，而非任意基因组上下文的功能信号。
---

## 摘要
动机
冷冻DNA编码器常被用作基因组特征提取器，但下游微调并未显示在其未改变的嵌入中哪些信息已经线性可及。我们提出MINA（核苷酸架构模型探询），这是一个轻量级探针基准，用于测试冷冻DNA嵌入能否恢复（i）每个基因的5类蛋白家族标签，以及（ii）每个基因自然语言摘要的1,536维GenePT嵌入。我们比较了经典编码序列和以转录起始位点为中心的基因组上下文之间的可恢复性。

结果
在来自五个家族的3,244个人类蛋白编码基因中，冷冻编码器从编码序列中最清晰地恢复了家族注释目标。带meanD池化的NT-v2达到了宏F1 0.828 / kappa 0.821，而CDS的4-mer基线为0.672 / kappa 0.702。与GenePT自然语言描述的对齐较弱。将所有四个编码器的CDS替换为196,608 bp以TSS为中心的窗口后，性能大幅下降，表明可恢复的信号主要是编码序列家族信号，而非来自任意基因组上下文的通用基因功能信号。

可用性和实现
源代码：https://github.com/Austin-Senna/dna_to_text；Python [≥]3.11。

联系方式
asw2215@columbia.edu

补充信息
补充表格、图表和可重复性细节包含在本预印本的结尾。

## Abstract
MotivationFrozen DNA encoders are often used as genomic feature extractors, but downstream fine-tuning does not show what information is already linearly accessible in their unchanged embeddings. We introduce MINA (Model Interrogation of Nucleotide Architectures), a lightweight probing benchmark for testing whether frozen DNA embeddings can recover (i) a 5-way protein-family label for each gene and (ii) the 1,536-dimensional GenePT embedding of each genes natural-language summary. We compare recoverability between canonical coding sequence and TSS-centred genomic contexts.

ResultsIn 3,244 human protein-coding genes from five families, frozen encoders recovered the family-annotation target most clearly from coding sequence. NT-v2 with meanD pooling reached macro-F1 0.828 /{kappa} 0.821, compared with 0.672 /{kappa} 0.702 for a CDS 4-mer baseline. Alignment to GenePT natural-language descriptions was weaker. Replacing CDS with 196,608 bp TSS-centred windows substantially reduced performance across all four encoders, indicating that the recoverable signal is primarily coding-sequence family signal rather than generic gene-function signal from arbitrary genomic context.

Availability and implementationSource code: https://github.com/Austin-Senna/dna_to_text; Python [&ge;]3.11.

Contactasw2215@columbia.edu

Supplementary informationSupplementary tables, figures, and reproducibility details are included at the end of this preprint.