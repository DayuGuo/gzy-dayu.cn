---
weight: 1
bookFlatSection: true
title: "建站指北"
---


## 网站简介
本博客使用Hugo + Github + Netlify + 阿里云域名 + Blogdown + Utterances搭建。除了阿里云域名需要少量付费，其他均为免费开源。

# 写在前面
本文没有很详细的教学，更多是分享我在学习过程中使用到的教程，并点出其中没有提到的要点。

# 准备工作
1. 注册Github，并下载Github Desktop。
2. 下载R和Rstudio，熟悉其基础用法，使用常见Package，如ggplot2和dplyr等。
3. 学习Markdown的基础语言，并了解什么是Rmarkdown。在这个阶段推荐使用Typora软件实践。
4. 用Rmarkdown（Rstudio的一个包）做一些简单的练习，并输出pdf或html。

# Hugo 和 Blogdown
传统个人网站的实现需要学习HTML、CSS和JavaScript，这对于一个非相关专业的业余Blogger来说负担有些大。而现在搭建个人网站已经变得越来越简单了，Github Page、Wordpress、Jekyll和Hugo都是很不错的选择。其中Wordpress的用户基数最大，有传言说白宫的部分网站也是用它搭建的，也是一个很不错的选择。如果你有个人云服务器，那选择和个性化就更高了。  
本网站由Hugo框架的Blogdown搭建，是因为研究生阶段的师兄很推荐Hugo。查阅相关资料后发现，这套系统已经很完善，且很好的**平衡了学习成本和个性化设置**。搭建这个网站的过程，其实也是一个学习R语言和个人网站相关语言的过程。对于一个非计算机专业的学生来说，这些东西还是挺有趣的，最后也挺有成就感的。

## Hugo简介
Hugo是由Go语言实现的静态网站生成器。简单、易用、高效、易扩展、快速部署。具体教程可见[Hugo官方文档](https://gohugo.io/documentation/)和[Hugo中文文档](https://www.gohugo.org/)。不过传统的Hugo搭建是没有很多图形化界面，大多由命令行实现，其实对新手不是很友好。

## Blogdown
所以本网站使用的是基于Hugo核心的[Blogdown](https://github.com/rstudio/blogdown)（R package）。这个包是谢益辉老师创建的，详细教程可见他的[《blogdown: Creating Websites with R Markdown》](https://bookdown.org/yihui/blogdown/)和[《用 blogdown搭建一个静态网站》](https://www.bilibili.com/video/BV1ZK4y1s7ir)。

在这里特别推荐庄闪闪的Blogdown教学。微信公众号：`庄闪闪的R语言手册`，其中有一篇“手把手带你搭建个人博客（汇总版）”，写的相当好。能够让大家少走很多弯路。这份教程中，从用Blogdown的使用到上线Netlify都有涉及。


## 选择你喜欢的主题
入门的时候推荐默认的主题，或是[hugo-theme-even](https://github.com/olOwOlo/hugo-theme-even), 其他主题见：[Hugo Themes](https://themes.gohugo.io/)。  
本Blog使用的是[Hugo-Book](https://github.com/alex-shpak/hugo-book)，是我比较喜欢的风格，且自带的插件比较多。

## 其他需要注意的
对于非计算机专业的使用者，有一些底层逻辑只能在实践的过程中慢慢摸索。
1. Blogdown的核心在于`config`文件，它的后缀可以使`.yaml`也可以是`.toml`，两种文件的语法不大一样，我推荐`config.toml`。载入themes之后，可以发现在`/themes`里会多一个主题文件夹，里面有默认的配置文件（`config.toml`）如有误操作，可以去那里找一份。一般默认的配置文件中会对设置有很详细的标注。
2. 在`\layouts`中有partials和shortcodes两个文件夹，分别代表了Hugo系统的两大插件形式。需要个性化设置的可以关注一下。
3. [Hugo-book](https://hugo-book-demo.netlify.app/)的示范网站里，有挺多Shortcodes模块的展示和教学，挺不错的。

# 阿里云域名
我大部分时间在国内，个人网址以后也可以有其他用途，就选了阿里云的域名。
以前的学习网站找不到了，大家可以参考这个：[github-netlify-阿里云配置](https://www.kancloud.cn/april_l/ssh-/968589)和[Hugo+Github+阿里云域名搭建个人博客（附Netlify部署方法）](https://taoziyu97.github.io/post/2021-1-11-build_blog/)。

# 评论区设置
这里介绍我使用过的两种。
## Disqus
教程可参考这一篇：[博客 | hugo 博客添加 disqus评论系统](http://www.360doc.com/content/20/1016/11/9422167_940736984.shtml)
不过我使用下来，这套系统有一些问题。
- 需要翻墙使用
- 载入速度慢
- 需要基于Disqus网站使用

## Utterances
本网站的评论系统通过[utteranc](https://utteranc.es/)搭建。  
utterances是一款基于Github Issue的Github工具,优点主要是无广告、加载快、配置简单，轻量开源!
### 操作步骤：
1. 建一个新的Github库，名字可以叫`Blogtalk`之类的，这个库专门存放评论。
2. 安装。utterances是一款Github app，安装很简单，在设置的时候选择`Blogtalk`。
3. 在config中添加：
```
## 配置 utteranc评论,教程参考 https://utteranc.es/
[params.utteranc]
  enable = false
  repo = "DayuGuo/blogtalks-utterances" ##换成自己得github库
  issueTerm = "title"
  theme = "github-light"
```
4. 更改html中的配置文件：
```
{{ if .Site.Params.utteranc.enable }}
<script src="https://utteranc.es/client.js"
repo="{{ .Site.Params.utteranc.repo }}"
issue-term="{{ .Site.Params.utteranc.issueTerm }}"
theme="{{ .Site.Params.utteranc.theme }}"
crossorigin="anonymous"
async>
</script>
{{ end }}
```
5. 在这个网站`https://utteranc.es/`配置。
```
<script src="https://utteranc.es/client.js"
        repo="DayuGuo/blogtalks-utterances"
        issue-term="title"
        theme="github-light"
        crossorigin="anonymous"
        async>
</script>
```

# 写在最后
在搭建了这个网站之后，偶尔会问自己，为什么一定要建“个人博客”，简书、知乎、微信公众号就不行吗？有什么区别呢？  
到现在，也快写了一年的Blog了，慢慢开始明白原因。  
我一直不是一个自信的人，很在乎“其他人”的看法。“多做多错”这种根深蒂固的想法也一直困扰着我。这些杂念纠缠在一起困扰着我，使得在公开场域表现自我对我来说是很困难的。  
想过很多次开个公众号或是简书，却总是下不了笔，一直没有发出第一篇文章。本质上也是对自己能力的不自信，和一些好高骛远，总是看着网上那些知名KOL的文章，幻想着第一篇就能写成那样。

而个人博客，是一种很微妙的存在，他开放，却又不在传统搜索引擎之中。不主动分享的话，它与我现有的社交网络就是分开的。我也很少会分享这个网站给其他人，仅在ins上标注了一下，默默期待着来访者。  
因为我知道，会点进来看的人，会是对我都是相对比较宽容的。  
这，让我少了很多负担；  
这，给我很大的安全感。；   
这，给了我写下去的勇气。  
在这里，我不用写很出色的文章，只要分享就好了。    

写的多了，发现，“内容”是什么并不重要。重要的是写的“过程”，这个过程包括了[阅读-收集-思考-协作]，让我的大脑动起来，似乎也是一个调整自我状态的过程。


Dayu
记于2022-03-30

 {{< button relref="/" >}}Get Home{{< /button >}}

<script src="https://utteranc.es/client.js"
        repo="DayuGuo/blogtalks-utterances"
        issue-term="title"
        theme="github-light"
        crossorigin="anonymous"
        async>
</script>




