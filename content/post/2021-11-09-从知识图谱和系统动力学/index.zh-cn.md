---
title: '从知识图谱和系统动力学 '
author: Zhaoyu
date: '2021-11-09'
slug: []
categories:
  - 学习笔记
tags:
  - 系统动力学
lastmod: '2021-11-09T15:15:49+08:00'
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
# 知识图谱和系统动力学

## 知识图谱（Knowledge Graph）

知识图谱是把所有不同种类的信息（Heterogeneous Information）连接在一起而得到的一个关系网络，具有以下几个特征：

- 由节点(Point)和边(Edge)组成
- 每个节点表示现实世界中存在的“实体”，每条边为实体与实体之间的“关系”
- 知识图谱是这种关系的最有效的表示方式

最初是对亲属和社交关系的描述，比如家族谱系和社交网络（Social Network）。后来随着各个领域的学科完整度不断提高，知识图谱在各个学科中均有使用。

<img src="/post/2021-11-09-从知识图谱和系统动力学/index.zh-cn_files/2560px-Conceptual_Diagram_-_Example.svg.png" alt="" width="20%"/>

## 系统动力学(System dynamics)

数据的收集和整理是全健康理念的重要组成部分。通过系统动力学框架分析数据间
的复杂关系并讨论其中的科学问题，是全健康相关课题中的重要组成部分。系统动力学
是一门分析研究系统反馈互动作用过程的流行理论，也是一门认识系统问题和解决系统
问题的综合学科。从系统论的观点看，系统动力学是结构方法、功能方法和历史方法的统
一。它基于系统论，吸收了控制论、信息论的精髓，是一门综合自然科学和计算机模拟技
术发展起来的学科。

![](/post/2021-11-09-从知识图谱和系统动力学/index.zh-cn_files/image-20211107220155485.png)

> 1. 系统动力学模型与知识图谱最大的区别在于，系统动力学模型是一个数学建模技术，通过数学方程描述节点之间的关系，最终达到**动态**演示的目的（如上图，其实是一个`.gif`文件，可以实现动态演示）。
>
> 2. 宏观上看，知识图谱具有节点、边、和方向，而系统动力学多了一个Loop的概念（因果反馈回路）。
> 3. 系统动力学模型中有存量和流量的概念。
> 4. 系统动力学中有延迟等概念存在。

主要步骤（wiki）:

- Define the problem boundary（尤为重要）
- Identify the most important stocks and flows that change these stock levels
- Identify sources of information that impact the flows
- Identify the main feedback loops
- Draw a causal loop diagram that links the stocks, flows and sources of information
- Write the equations that determine the flows
- Estimate the parameters and initial conditions. These can be estimated using statistical methods, expert opinion, market research data or other relevant sources of information.
- Simulate the model and analyse results.

除了技术上的难度，数据的完整性是系统动力学模型实现的最大困难之一。在定义了系统的边界和节点后，任何一个节点的损失都对系统动力学模型的准确度有巨大影响。

如果是从流行病学展开讨论，简单地说就如下图所示，需要有一定的学科基础和数据基础才能实现系统动力学建模。

流行病现状调查和基础数据的完整度是一切的基础。加入更多元素和数据，可以构建不同目的的模型。

基础的疾病动力学模型（SIR）可以简单描述和推导疫情的发展趋势。

复杂的疾病动力学模型会加上疾病传播链上的各中间宿主，这部分就需要实验室建模获取的数据了。

最优控制模型可以评估不同疾病干预措施的有效性。

这几个部分的研究存在一定的递进性。

![](/post/2021-11-09-从知识图谱和系统动力学/index.zh-cn_files/image-20211107224201729.png)

目前针对复杂系统的研究热点是涌现、因果推断和自组织自适应这些概念。因果推断在数据不断完整的基础上，着手于探索复杂情境下因果关系的建立。涌现一定程度上描述混沌对系统的影响。

## 以系统性思维绘制知识图谱

疾病系统动力学模型可以如上图所示那样进行，定义了边界和节点之后，关系（也就是数据）可以用Meta分析的方式收集。但如果是讨论 One Health 这样的复杂整体，实际上是很难实现的，即使抛开很多其他因素，时间序列的数据就无法获取。

![](/post/2021-11-09-从知识图谱和系统动力学/index.zh-cn_files/image-20211107225115097.png)

以系统性思维绘制知识图谱并构建指标是可以实现的。上图中，左图是以系统性思维绘制的知识图谱，图中已经可以看到存量和流量概念的雏形。


