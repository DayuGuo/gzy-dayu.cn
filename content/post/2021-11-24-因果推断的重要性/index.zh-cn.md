---
title: 因果推断的重要性
author: Zhaoyu
date: '2021-11-24'
categories:
  - 学习笔记
tags:
  - 系统动力学
lastmod: '2021-11-24T09:20:15+08:00'
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

在数据分析的过程中，我们常会面对具有相关关系的数据，在不同情境下需要以不同的角度理解这组数据。很多情况下，具有相关关系的数据并不具有因果关系（如下图，数据来自`https://www.tylervigen.com/spurious-correlations`）。

![](/post/2021-11-24-因果推断的重要性/index.zh-cn_files/截屏2021-11-24 09.24.12.jpg)


因果一般指原因A与其引发的现象B，但A和B可能都是由C引发的现象，AB之间并没有因果关系。另外，相关性并不只有线性关系，也并不只有correlation coefficient为1的情况下才能说两个变量具有相关性，想要更深入理解这个概念还需继续学习统计学。
因果关系分为三层，第一层是association，第二层是intervention (P(y | do(X), 即由于做了X而带来了多少y的变化)，第三层是counterfactual。p值展示的是第一层的相关性，且在因果关系已经确定好的情况下，可以证明第二层的因果关系的强弱。
