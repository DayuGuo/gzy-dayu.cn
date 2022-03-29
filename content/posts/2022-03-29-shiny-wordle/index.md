---
title: 用Shiny造一个自己的Wordle网站
author: Dayu
date: '2022-03-29'
slug: shiny-wordle
categories:
  - 兴趣
tags:
  - R
  - 艺术
---

# 什么是Wordle

从分类上看，Wordle 和填字游戏都属于字谜游戏的一种。在英语国家，字谜游戏有悠久的历史和广泛的受众，变化也很多样，填字游戏则是其中最具代表性的。  

<img src="images/screenshot-final.png" alt="" width="50%" height="50%"/>  
而Wordle在难度和形态上都大大简化：这个游戏每天更新一期，玩家唯一目标，就是在六次尝试机会之内，猜出一个五个字母的单词。

为此，游戏界面是一个5×6的方块阵列。玩家通过下方键盘输入猜测结果后，游戏会给字母方块标上颜色，提示猜测的准确性：

绿色 :green_square:：说明答案里有这个字母、所在位置也正确；  
黄色 :yellow_square:：说明答案里有这个字母、但不在这个位置；  
灰色 :white_large_square:：说明答案里没有这个字母。

然后，玩家根据获得的提示继续尝试，直到猜对答案，或者用尽六次机会。

游戏结束后，会给玩家提供一份统计数据，显示各步骤的正确率、连续游玩的天数和下一局上线的倒计时；同时，会将玩家的游戏界面生成对应颜色布局的 emoji 矩阵，点击「share」按钮即可复制分享------这也就是文章开头那种密电一般推文的来源。 （千万别清cookies... 我之前几百天的记录一下就这么没了）

Wordle 虽然规则简单，但其实自带了很多促进传播的属性。首先，Wordle 一天只更新一道题目，这种人为制造的稀缺性增强了玩家的挑战欲和期待感。其次，Wordle 的分享功能设计巧妙：用 emoji 色块指代游戏战果，不仅极具辨识度，而且易于传播，又避免了剧透。此外，字谜游戏在欧美国家的传统人气、简单易上手的游戏设计，都一定程度上促进了 Wordle 的火热。

# 用Shiny造一个自己的Wordle网站

通过这篇R-bloggers上的教程就能搭建属于自己的Wordle网站。  
我的成果：<https://dayuguo.shinyapps.io/mywordle/>

> Reference:
>
> 1.  <https://www.r-bloggers.com/2022/03/shiny-wordle-word-journey/>
