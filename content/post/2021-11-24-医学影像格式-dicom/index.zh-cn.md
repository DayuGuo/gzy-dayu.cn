---
title: 医学影像格式-DICOM
author: Zhaoyu
date: '2021-11-24'
slug: []
categories:
  - 学习笔记
tags:
  - 影像组学
lastmod: '2021-11-24T09:46:54+08:00'
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
## DICOM格式
Digital Imaging and Communications in Medicine（DICOM）是医疗成像信息和相关数据的通信和管理标准，包含了图像的格式和网络传输协议。由美国ACR、NEMA、AAPM和RSNA四大学会一同创建。1993年更新了3.0版，也是当下被应用最广的格式，它涵盖几乎所有临床医学影像，包括X射线，CT，核磁共振，超声等。
 1. DICOM文件由Header头文件以及Image影像两部分构成。
 2. 主要包括四类信息：Patients病人信息，Study检查信息，Series序列信息以及Image图像信息。  
  - 病人信息主要包括患者姓名、性别、ID等。  	
  - 检查信息包括检查号、检查时间、检查部位等。  
  - 序列信息包括检查模态（MRI，CT，DR等），影像层厚等信息。  
  - 影像信息对医学影像相关的研究可能至关重要，因为里面包含了图像采样率、分辨率、像素物理间距等等。  
  - 从这里我们可看到，例如我们想计算ROI（感兴趣区）体积时，Header中的像素物理距离就成了必不可少的。而这是png、jpg文件无法提供的。
3. BMP的文件能满足人眼辨别的极限。是把DICOM的图像映射到0-256灰度级之间。


