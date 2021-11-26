---
title: 影像组学研究指南
author: Zhaoyu
date: '2021-11-26'
slug: []
categories:
  - 学习笔记
tags:
  - 影像组学
lastmod: '2021-11-26T09:19:14+08:00'
keywords: []
description: ''
comment: no
toc: no
autoCollapseToc: no
postMetaInFooter: no
hiddenFromHomePage: no
contentCopyright: no
reward: no
mathjax: no
mathjaxEnableSingleDollar: no
mathjaxEnableAutoNumber: no
hideHeaderAndFooter: no
flowchartDiagrams:
  enable: no
  options: ''
sequenceDiagrams:
  enable: no
  options: ''
---


1. 应明确定义图像数据集，如训练集、验证集和测试集。三者不应有重合的部分，且需要明确纳入和排出标准。
2. 最终的产出的测试数据集最好使用外部数据集，这样有助于研究和模型的推广。
3. 数据集从多中心多渠道收集，可以使用一些开源的数据库。同一个医院同一机器的数据集可能对模型存在潜在的影响。
4. 训练集、验证集和测试集的数据规模需要足够大。这个“足够”的定义可以通过软件计算，也可以通过过往经验总结，不同的模型对数据规模的要求并不相同。
5. 应使用临床影像诊断标准共识作为图像标签的基准。
6. 需要描述医学影像的预处理过程。
7. 人工智能算法的性能应该与影像学专家进行比对，如能超越影像学专家的准确性，说明该模型具有实际价值。
8. AI算法的机制需要尽可能的描述，尽量使用可解释的架构。不能只使用AUC进行分析总结，应结合多指标进行评估，如敏感性、特异性、PPV和NPV。
9. 尽可能的将代码和数据集以某种形式公开，不一定是完全免费的，但提供数据的获取途径。这样有助于结果的验证，并避免重复研究。
10. 影像采集协议需要标注清晰，包括设备型号和扫描参数等。
11. 尽可能的结合影像学数据和临床数据。


## Reference
1. 本文大部分内容来自 Daniel Pinto dos Santos老师的Blog：`https://ai.myesr.org/publications/why-radiomics-research-does-not-translate-to-clinical-practice-evaluation-of-literature-using-rqs-and-tripod/`
2. B站Li的直播：`https://space.bilibili.com/542601735?from=search&seid=841881887859990693&spm_id_from=333.337.0.0`



