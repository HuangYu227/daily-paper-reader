---
title: "Computation-through-DynamicsToolkit: Simulated datasets and quality metrics for dynamical models of neural activity"
title_zh: 动态计算工具包：神经活动动力学模型的模拟数据集与质量指标
authors: "Versteeg, C., McCart, J. D., Ostrow, M., Zoltowski, D. M., Washington, C. B., Driscoll, L., Codol, O., Michaels, J. A., Linderman, S. W., Sussillo, D., Pandarinath, C."
date: 2026-06-05
pdf: "https://www.biorxiv.org/content/10.1101/2025.02.07.637062v3.full.pdf"
tags: ["query:tsc"]
score: 7.0
evidence: 生成神经动力学模拟时间序列数据
tldr: 神经科学中，理解神经计算需依赖动力学模型，但现有合成数据集缺乏生物学特征，且缺乏验证模型准确性的标准指标。CtDToolkit提供了模拟生物神经回路计算特性的合成数据集、可解释的性能指标以及标准化训练评估流程。使用该工具包可指导模型开发、调试与优化，为研究神经计算提供可靠基准。
source: biorxiv
selection_source: fresh_fetch
motivation: 现有合成数据集缺乏生物神经回路的关键特征，且缺乏量化模型动态推断准确性的有效指标，限制了动力学模型的验证与改进。
method: CtDToolkit提供三类资源：反映神经计算特性的合成数据集、可解释的模型性能指标、以及包含或不含外部输入的标准化训练评估流程。
result: 工具包通过示例展示了如何利用这些资源指导神经动力学模型的开发、调优与故障排除，提升模型在真实数据上的可信度。
conclusion: CtDToolkit为模型开发者提供了必要框架，通过动力学视角更深入地表征和理解神经计算，推动解码大脑从感觉到行为的信息处理机制。
---

## 摘要
系统神经科学的一个主要目标是发现神经元群体如何将输入转化为目标导向行为，这一过程称为神经计算。理解神经计算的一个强大框架是利用神经动力学——即控制神经活动随时间演变的规则——来解释目标导向的输入-输出转换是如何发生的。由于动力学规则不可直接观测，我们需要能够从记录的神经活动中推断神经动力学的计算模型。通常我们使用已知真实动力学的合成数据集来验证这类模型，但遗憾的是，现有的合成数据集并未反映神经计算的基本特征，因此可能无法很好地代表神经系统。此外，该领域缺乏经过验证的指标来量化模型推断的动力学的准确性。动态计算工具包（CtDToolkit）通过提供以下内容填补了这些关键空白：1）反映生物神经回路计算特性的合成数据集，2）用于量化模型性能的可解释指标，以及3）用于训练和评估模型（无论是否有已知外部输入）的标准化流程。在本文中，我们展示了CtDToolkit如何帮助指导神经动力学模型的开发、调优和故障排除。总之，CtDToolkit为模型开发者提供了一个必要的框架，以通过动力学的视角更好地理解和描述神经计算。

作者总结：理解大脑的工作原理需要对神经元群体如何处理信息以产生行为进行可解释的描述。一种强有力的方法是研究"神经动力学"，即神经活动随时间演变的模式。科学家们开发计算模型从神经记录中推断这些动力学，但判断推断的动力学是否可信一直具有挑战性。现有数据集往往缺乏生物神经回路的关键特征，而当前的性能指标可能无法全面反映模型质量。

我们开发了动态计算工具包（CtDToolkit）来解决这些问题。该工具包提供了三个关键资源：受生物学启发的合成数据集、提供更全面模型性能描述的改进指标，以及用于训练和评估模型的标准化工作流程。我们希望CtDToolkit能让研究人员在将模型应用于真实脑数据之前，对其严格测试、改进和排错。这项工作为开发更好的方法理解神经计算奠定了关键基础，最终将推进我们解码大脑如何将感觉信息转化为思维和行动的能力。

## Abstract
A primary goal of systems neuroscience is to discover how ensembles of neurons transform inputs into goal-directed behavior, a process known as neural computation. A powerful framework for understanding neural computation uses neural dynamics - the rules that govern how neural activity evolves over time - to explain how goal-directed input-output transformations occur. As dynamical rules are not directly observable, we need computational models that can infer neural dynamics from recorded neural activity. We typically validate such models using synthetic datasets with known ground-truth dynamics, but unfortunately existing synthetic datasets dont reflect fundamental features of neural computation and may therefore be poor proxies for neural systems. Further, the field lacks validated metrics for quantifying the accuracy of the dynamics inferred by models. The Computation-through-Dynamics Toolkit (CtDToolkit) addresses these critical gaps by providing: 1) synthetic datasets that reflect computational properties of biological neural circuits, 2) interpretable metrics for quantifying model performance, and 3) a standardized pipeline for training and evaluating models with or without known external inputs. In this manuscript, we demonstrate how CtDToolkit can help guide the development, tuning, and troubleshooting of neural dynamics models. In summary, CtDToolkit provides a necessary framework for model developers to better understand and characterize neural computation through the lens of dynamics.

Author SummaryUnderstanding how the brain works requires interpretable accounts of how populations of neurons process information to produce behavior. One powerful approach is to study "neural dynamics", the patterns of how neural activity evolves over time. Scientists develop computational models to infer these dynamics from neural recordings, but it has been challenging to know when the inferred dynamics are trustworthy. Existing datasets often lack key features of biological neural circuits, and current performance metrics can provide an incomplete picture of model quality.

We developed the Computation-through-Dynamics Toolkit (CtDToolkit) to solve these problems. Our toolkit provides three key resources: biologically motivated synthetic datasets, improved metrics that provide more holistic accounts of model performance, and a standardized workflow for training and evaluating models. We hope that CtDToolkit enables researchers to rigorously test, improve, and troubleshoot their models before applying them to real brain data. This work establishes a crucial foundation for developing better methods to understand neural computation, ultimately advancing our ability to decode how the brain transforms sensory information into thought and action.