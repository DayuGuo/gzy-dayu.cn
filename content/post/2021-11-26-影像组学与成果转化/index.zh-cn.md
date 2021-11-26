---
title: 影像组学与成果转化
author: Zhaoyu
date: '2021-11-26'
slug: []
categories:
  - 学习笔记
tags:
  - 影像组学
lastmod: '2021-11-26T08:23:16+08:00'
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

在过去的十年里，使用影像组学技术完成的医工交叉项目变得越来越多。截止到2019年，PubMed上的相关研究已经超过4000项。不过，其中完成成果转化和临床应用的项目非常的少。是什么导致了这样的结果呢？

近期一篇文章回顾性的分析了这一问题。首先，这个项目设定了一个文章的筛选机制，尽可能的选入高影响因子的期刊，以提升研究的可靠性。接着，通过定量和定性的指标去评估这些文章的质量。RQS和TRIPOD指南是目前影响力最大的两份技术文档，TRIPOD提供了一份完整的Checklist，可以作为客观的定性指标进行评估。结果表明，在这些影像组学文章中，RQS的平均分仅有26%，TRIPOD的评分仅有58%。

> Park J E, Kim D, Kim H S, et al. Quality of science and reporting of radiomics in oncologic studies: room for improvement according to radiomics quality score and TRIPOD statement[J]. European radiology, 2020, 30(1): 523-536.

- 纳入的77项研究中，仅有一项研究公布了影像采集协议
- 45%的研究进行了感兴趣区的多次分割
- 70.1%的研究没有使用多中心的数据retain验证
- 28%的研究结合了临床信息
- 仅3项研究公开了研究代码和数据

影像组学研究的总体质量仍有很大的提升空间，特别是在结果的可重复性、临床效果评估和开源社群的建立等方面。Daniel着重提到：这些评估结果不应用来贬低现有的研究，学科和技术发展初期总会面临很多复杂的问题。应该更多的鼓励讨论和推广标准。


## Key points

- 影像组学整体的研究质量和科学性欠佳。
- RQS体系在临床应用、可重复性、前瞻性和开放科学等方面比较欠缺。
- TRIPOD体系在研究目标的确立、盲法评估、样本量、数据缺失说明等方面比较欠缺。

所以在从事影像组学工作的时候，需要结合RQS和TRIPOD两种体系进行实验设计和回顾验证，在实验设计初期避免可能存在的问题。期待未来影像组学会有Meta分析那样标准化的工作流，这不仅需要影像组学工作者的努力，还需要标准化临床数据库的支持，数据安全和完善变得越来越重要。

## 影像组学研究概况

<img src="/post/2021-11-26-影像组学与成果转化/index.zh-cn_files/Fig_2_pds-1080x765.jpg" alt="" width="80%"/>

总结：
- 尽管影像组学在未来有很好的应用前景，但需要更好更标准的实验流程以保证数据和结果的可靠性。
- Translation Gap，成果转化问题已经变得越来越严重。
- 理想情况下，需要与更多临床上的前瞻性研究相结合。

现在国内对成果转化的重视程度也越来越高了，最新的职称评定指南中标注了专利的重要性。

## Reference：

1. 本文大部分内容来自 Daniel Pinto dos Santos老师的Blog：`https://ai.myesr.org/publications/why-radiomics-research-does-not-translate-to-clinical-practice-evaluation-of-literature-using-rqs-and-tripod/`
2. B站`有Li`的直播：`https://space.bilibili.com/542601735?from=search&seid=841881887859990693&spm_id_from=333.337.0.0`
3. Lambin P, Leijenaar RTH, Deist TM et al (2017) Radiomics: the bridge between medical imaging and personalized medicine. Nat Rev Clin Oncol 14:749–762
4. Moons KG, Altman DG, Reitsma JB et al (2015) Transparent reporting of a multivariable prediction model for individual prognosis or diagnosis (TRIPOD): explanation and elaboration. Ann Intern Med 162:W1–W73
5. Park J E, Kim D, Kim H S, et al. Quality of science and reporting of radiomics in oncologic studies: room for improvement according to radiomics quality score and TRIPOD statement[J]. European radiology, 2020, 30(1): 523-536.