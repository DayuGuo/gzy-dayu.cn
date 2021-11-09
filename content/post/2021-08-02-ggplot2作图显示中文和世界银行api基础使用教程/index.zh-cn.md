---
title: ggplot2作图显示中文和世界银行API基础使用教程
author: Zhaoyu
date: '2021-08-02'
slug: []
categories:
  - 学习笔记
tags:
  - R
  - 中文
  - 世界银行API
lastmod: '2021-08-02T15:01:24+08:00'
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
在使用ggplot作图的时候，我们经常需要使用中文作图，用sysfonts、showtextdb和showtext这三个包可以简单的实现这一功能。 

  另外，我们数据的处理和收集过程中，我们需要调用各种API，本文中提到的WDI世界银行的世界发展指标数据库是一个简单的常用包。

**1. 准备工作环境：**

```
# 载入包（示例）
install.packages("WDI")
# 通过API获取世界银行的数据
library(WDI)
# 数据处理包
library(tidyverse)
# 显示中文包，三个包需要依次载入
library(sysfonts)
library(showtextdb)
library(showtext)
# 载入经典的可视化包
library(ggplot2)
```

**2. 数据提取**

```
# 列出可用数据集
wdi_datasets <- WDIsearch()
# 查看数据集
head(wdi_datasets)

# 抓取其中一个数据集
wdi_trade_in_services <- WDI(indicator = "BG.GSR.NFSV.GD.ZS")
# 查看数据集简介
str(wdi_trade_in_services)
# 选择我们要的数据，这里选择了中国的
cndata <- wdi_trade_in_services %>%
    filter(iso2c == "CN")
```

**3.作图和显示中文**

```
# 激活显示中文的包
showtext_auto()

# 作图
cnplot <- ggplot(cndata, aes(year, BG.GSR.NFSV.GD.ZS)) +#设置点的颜色和大小
    geom_point(color = "violet", shape = 20) + #插入标题
    ggtitle("我是标题")
```

**4.输出：**

作者：Dayu

校稿：Anderson