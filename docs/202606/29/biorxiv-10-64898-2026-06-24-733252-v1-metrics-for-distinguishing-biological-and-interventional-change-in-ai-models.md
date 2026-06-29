---
title: Metrics for Distinguishing Biological and Interventional Change in AI Models
title_zh: AI模型中区分生物变化与干预变化的指标
authors: "Ewing, M. A."
date: 2026-06-29
pdf: "https://www.biorxiv.org/content/10.64898/2026.06.24.733252v1.full.pdf"
tags: ["query:tsc"]
score: 6.0
evidence: 区分纵向数据中生物变化与干预变化的度量
tldr: 纵向数据分析中，生物变化与干预变化常因依赖稳定轨迹而混淆，导致模型预测置信地错误。本文从数据底层提出曲率偏移与变形风险两个指标，量化干预事件在轨迹上的几何特征。在ADNI数据集上，模型对两类事件后观测的符号准确率仅0.35，两指标在事件后均显著升高2.2倍且高度耦合。该度量实现对每个个体检测模型参考是否失效，并区分变化是否具有干预特征。
source: biorxiv
selection_source: fresh_fetch
motivation: 现有方法依赖因果假设或隐变量模型，未能从数据底层区分生物变化与干预变化。
method: 提出Curvature Shift和Deformation Risk两个个体级度量，分别刻画事件前后轨迹斜率变化及观测偏离程度。
result: 在ADNI 309名受试者中，两指标在生物事件和干预后分别升高2.23倍和2.26倍，预测符号准确率仅约0.35。
conclusion: 该度量可个体化检测模型参考失效，并识别变化是否携带干预的几何特征。
---

## 摘要
纵向生物数据的统计与机器学习模型通过将每个新观测值与先前观测所隐含的轨迹进行比较来评估变化，并假设生成该轨迹的过程是稳定的。我们使用数据基质（data substrate）一词来指代纵向数据的底层结构，它独立于模型的架构或容量，决定了任何此类模型能够恢复的信息。当生成过程发生变化时，无论是通过生物转型还是外部干预，先前的轨迹就不再是有效的参考，外推预测可能自信地出错，且没有内部信号表明参考已失效。一个明确且公认的困难在于，生物变化和干预变化仅通过假设轨迹下的序列时间比较来观测，很容易被混淆；现有方法通过因果假设或隐藏混杂模型来处理这一问题，而非从数据基质本身出发。本文探讨是否可以在基质层面区分两者，并引入两个受试者级别的指标来量化干预变化在数据中留下的几何特征：曲率偏移（Curvature Shift），即事件前后轨迹斜率的变化；以及变形风险（Deformation Risk），即事件后观测值与先前轨迹参考的偏离。我们使用阿尔茨海默病神经影像学倡议（ADNI）中309名人类受试者的纵向认知测量数据来评估这一条件，该大型纵向数据集包含同一受试者中两个不同的、预先定义的状态转换事件：一个生物转型和一个干预。外推事件前轨迹的模型将大约三分之二的事件后观测值赋予了错误的变化方向（生物事件后事件后符号准确率为0.341，干预后为0.350，而随机概率为0.50）；仅有11%的生物事件后和12%的干预后读数与先前动态保持一致，而更高容量的多层感知器重复了该错误而非解决了它。生物事件后曲率偏移高出2.23倍（p = 4.4e-8），干预后高出2.26倍（p = 7.4e-8），并且这两个指标相互耦合（rho = 0.500；95% CI，0.407至0.587）。结果在独立终点上得到复现，并经受住了倾向性匹配、置换和留一法验证。这些指标可逐一检测每个受试者中，拟合模型的参考何时不再支配数据，以及偏离是否带有干预变化的几何特征。

## Abstract
Statistical and machine-learning models of longitudinal biological data evaluate change by comparing each new observation against the trajectory implied by prior observations, assuming the process generating that trajectory is stable. We use data substrate to mean the underlying structure of the longitudinal data that determines what any such model can recover, independent of its architecture or capacity. When the generating process changes, whether through a biological transition or through an external intervention, the prior trajectory ceases to be a valid reference, and extrapolated predictions can be confidently wrong with no internal signal that the reference has failed. A distinct and recognised difficulty is that biological change and interventional change, observed only through serial intertemporal comparison under an assumed trajectory, are readily conflated; existing approaches address this through causal assumptions or hidden-confounder models rather than from the data substrate itself. Here we ask whether the two can be distinguished at the substrate level, and we introduce two subject-level metrics that quantify the geometric signature an interventional change leaves in the data: Curvature Shift, the change in trajectory slope across the event, and Deformation Risk, the departure of post-event observations from the prior-trajectory reference. We evaluate the condition on longitudinal cognitive measurements from 309 human subjects in the Alzheimer Disease Neuroimaging Initiative (ADNI), a large longitudinal dataset containing two distinct, ex-ante-defined regime-change events in the same subjects: a biological transition and an intervention. A model extrapolating the pre-event trajectory assigned the wrong direction of change to roughly two-thirds of post-event observations (post-event sign accuracy 0.341 after the biological event and 0.350 after the intervention, against a chance value of 0.50); only 11% of post-biological-event and 12% of post-intervention readings remained concordant with prior dynamics, and a higher-capacity multilayer perceptron reproduced rather than resolved the error. Curvature Shift was 2.23-fold higher after the biological event (p = 4.4e-8) and 2.26-fold higher after the intervention (p = 7.4e-8), and the two metrics were coupled (rho = 0.500; 95% CI, 0.407 to 0.587). Findings replicated on an independent endpoint and survived propensity matching, permutation, and leave-one-out. The metrics detect, per subject, when the reference of a fitted model has stopped governing the data and whether the departure carries the geometric signature of an interventional change.