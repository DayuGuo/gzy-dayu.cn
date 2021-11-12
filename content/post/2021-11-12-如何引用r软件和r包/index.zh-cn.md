---
title: 如何引用R软件和R包？
author: Zhaoyu
date: '2021-11-12'
slug: []
categories:
  - 学习笔记
tags:
  - R
lastmod: '2021-11-12T18:33:31+08:00'
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


## 为什么要引用？

1. **关注开发者贡献（Developer Credit）**

   很多R包的开发者本身也是科研人员，他们利用自己的业余时间为大家开发好用开源的R包。如果没有得到引用，那么他们的功劳并没有得到体现。高质量开源软件开发的可持续发展需要开发者和使用者的一同努力。

2. **可重复性（Repeatable Science）**

   引用实验中使用的软件不仅可以帮助其他科学家顺利复现您的实验，还能够帮助软件宣传。

   明确数据和工具的来源，才有实验重复的基础。科学实验中使用的软件名和版本号都是很重要的信息。目前，科学出版物中软件的正确引用已经成为一个普遍性的问题，[FORCE11 Software Citation Implementation Working Group](https://www.force11.org/group/software-citation-implementation-working-group) 就是为了这一现象而成立的。

   Note：可重复性（*Repeatability*）和可复现（*Reproducibility*）是两个不同的概念。

   我的个人理解是，可重复性代表实验流程可以重复，而可复现代表实验结果可以一致，并不是所有实验可以做到可复现。

3. **感激（Gratitude）**

   引用也是对开发者工作的一种感谢方式，甚至有助于提升开发者的简历。

   >  I know that every citation I get for my [weathercan](https://docs.ropensci.org/weathercan) package warms my heart 😻 (and helps my CV)!

## 哪些包需要引用？

很多研究人员赞同引用R包，但我们是否应该引用所有使用到R包呢？

理论上，我们应该引用实验中所有使用到的R包。（如果你使用`magick`进行图像处理，或是使用`tidyhydat`检索水文数据，那么你一定要引用他们）

但在真实情境下，这个问题确实很难回答，因为我们在进行科学研究的过程中，会使用很多功能不同的R包，每个包起到的作用大小各有不同，比如数据挖掘包，或是`osfr`这种常用包。在理想情境下，我们所有使用的包都该被引用，但编辑和作者对这方面的认识均有不足，所以很难实现。

FORCE11 软件引用规范化小组提出的建议是：引用研究中最重要的包。

必须补充的一点是，引用开源软件并不是一件坏事，开源软件是我们工作流程的一部分。接下来我会分享一些引用的技巧，希望可以帮助到大家。

## 怎么引用R

引用R软件很简单

```r
citation()
```

```r
## 
## To cite R in publications use:
## 
##   R Core Team (2021). R: A language and environment for statistical
##   computing. R Foundation for Statistical Computing, Vienna, Austria.
##   URL https://www.R-project.org/.
## 
## A BibTeX entry for LaTeX users is
## 
##   @Manual{,
##     title = {R: A Language and Environment for Statistical Computing},
##     author = {{R Core Team}},
##     organization = {R Foundation for Statistical Computing},
##     address = {Vienna, Austria},
##     year = {2021},
##     url = {https://www.R-project.org/},
##   }
## 
## We have invested a lot of time and effort in creating R, please cite it
## when using it for data analysis. See also 'citation("pkgname")' for
## citing R packages.
```

然后，需要获取R的版本号

```r
version$version.string
```

```r
## [1] "R version 4.1.2 (2021-11-01)"
```

在文章方法学的描述性部分，我建议如下：

> All analyses were performed using R Statistical Software (v4.1.2; R Core Team 2021)

## 如何引用R包

R包的详细信息也可以通过R软件获得。

一些R包的开发者会发布论文，并期望软件的使用者引用。

```r
citation("weathercan")
```

```r
## 
## To cite 'weathercan' in publications, please use:
## 
##   LaZerte, Stefanie E and Sam Albers (2018). weathercan: Download and
##   format weather data from Environment and Climate Change Canada. The
##   Journal of Open Source Software 3(22):571. doi:10.21105/joss.00571.
## 
## A BibTeX entry for LaTeX users is
## 
##   @Article{,
##     title = {{weathercan}: {D}ownload and format weather data from Environment and Climate Change Canada},
##     author = {Stefanie E LaZerte and Sam Albers},
##     journal = {The Journal of Open Source Software},
##     volume = {3},
##     number = {22},
##     pages = {571},
##     year = {2018},
##     url = {https://joss.theoj.org/papers/10.21105/joss.00571},
##   }
```

你可以通过 `packageVersion()` 获取包的版本号。

```r
packageVersion("weathercan")
## [1] '0.6.2'
packageVersion("magick")
## [1] '2.7.3'
```

在文章方法学的描述性部分，我建议如下：

> All analyses were performed using R Statistical Software (v4.1.2; R Core Team 2021). Temperature data was obtained from Environment and Climate Change Canada via the weathercan R package (v0.6.2; LaZerte and Albers 2018). Vegetation photos were simplified and processed prior to analysis using the magick R package (v2.7.3; Ooms 2021).

如果已经在环境中使用了大量的包，则可以用knitr的`write_bib`函数批量导出，并写出bib格式的文件：

```r
knitr::write_bib(c(  .packages() ), file =  'packages.bib')
```

## 系统性的管理引用

在文件管理的过程中，你可以用rmarkdown输出文本，并在末尾加入 `sessionInfo()` 或devtools::session_info()。效果如下：

```r
devtools::session_info()
## ─ Session info ───────────────────────────────────────────────────────────────
##  setting  value                       
##  version  R version 4.1.2 (2021-11-01)
##  os       Ubuntu 20.04.3 LTS          
##  system   x86_64, linux-gnu           
##  ui       X11                         
##  language en_CA:en                    
##  collate  en_CA.UTF-8                 
##  ctype    en_CA.UTF-8                 
##  tz       America/Winnipeg            
##  date     2021-11-09                  
## 
## ─ Packages ───────────────────────────────────────────────────────────────────
##  package     * version    date       lib source                     
##  assertthat    0.2.1      2019-03-21 [1] CRAN (R 4.1.0)             
##  bslib         0.3.0      2021-09-02 [1] CRAN (R 4.1.1)             
##  cachem        1.0.6      2021-08-19 [1] CRAN (R 4.1.1)             
##  callr         3.7.0      2021-04-20 [1] CRAN (R 4.1.0)             
##  cli           3.1.0      2021-10-27 [1] CRAN (R 4.1.2)             
##  crayon        1.4.2      2021-10-29 [1] CRAN (R 4.1.2)             
##  desc          1.4.0      2021-09-28 [1] CRAN (R 4.1.1)             
##  devtools      2.4.1      2021-05-05 [1] CRAN (R 4.1.0)             
##  digest        0.6.28     2021-09-23 [1] CRAN (R 4.1.1)             
##  ellipsis      0.3.2      2021-04-29 [1] CRAN (R 4.1.0)             
##  emo           0.0.0.9000 2021-06-04 [1] Github (hadley/emo@3f03b11)
##  evaluate      0.14       2019-05-28 [1] CRAN (R 4.1.0)             
##  fastmap       1.1.0      2021-01-25 [1] CRAN (R 4.1.0)             
##  fs            1.5.0      2020-07-31 [1] CRAN (R 4.1.0)             
##  generics      0.1.0      2020-10-31 [1] CRAN (R 4.1.0)             
##  glue          1.5.0      2021-11-07 [1] CRAN (R 4.1.2)             
##  htmltools     0.5.2      2021-08-25 [1] CRAN (R 4.1.1)             
##  jquerylib     0.1.4      2021-04-26 [1] CRAN (R 4.1.0)             
##  jsonlite      1.7.2      2020-12-09 [1] CRAN (R 4.1.0)             
##  knitr         1.36       2021-09-29 [1] CRAN (R 4.1.2)             
##  lifecycle     1.0.1      2021-09-24 [1] CRAN (R 4.1.1)             
##  lubridate     1.8.0      2021-10-07 [1] CRAN (R 4.1.1)             
##  magrittr      2.0.1      2020-11-17 [1] CRAN (R 4.1.0)             
##  memoise       2.0.0      2021-01-26 [1] CRAN (R 4.1.0)             
##  pkgbuild      1.2.0      2020-12-15 [1] CRAN (R 4.1.0)             
##  pkgload       1.2.3      2021-10-13 [1] CRAN (R 4.1.1)             
##  prettyunits   1.1.1      2020-01-24 [1] CRAN (R 4.1.0)             
##  processx      3.5.2      2021-04-30 [1] CRAN (R 4.1.0)             
##  ps            1.6.0      2021-02-28 [1] CRAN (R 4.1.0)             
##  purrr         0.3.4      2020-04-17 [1] CRAN (R 4.1.0)             
##  R6            2.5.1      2021-08-19 [1] CRAN (R 4.1.1)             
##  remotes       2.4.0      2021-06-02 [1] CRAN (R 4.1.0)             
##  rlang         0.4.12     2021-10-18 [1] CRAN (R 4.1.1)             
##  rmarkdown     2.11       2021-09-14 [1] CRAN (R 4.1.2)             
##  rprojroot     2.0.2      2020-11-15 [1] CRAN (R 4.1.0)             
##  rstudioapi    0.13       2020-11-12 [1] CRAN (R 4.1.0)             
##  sass          0.4.0      2021-05-12 [1] CRAN (R 4.1.0)             
##  sessioninfo   1.1.1      2018-11-05 [1] CRAN (R 4.1.0)             
##  stringi       1.7.5      2021-10-04 [1] CRAN (R 4.1.1)             
##  stringr       1.4.0      2019-02-10 [1] CRAN (R 4.1.0)             
##  testthat      3.1.0      2021-10-04 [1] CRAN (R 4.1.1)             
##  usethis       2.1.3      2021-10-27 [1] CRAN (R 4.1.2)             
##  withr         2.4.2      2021-04-18 [1] CRAN (R 4.1.0)             
##  xfun          0.28       2021-11-04 [1] CRAN (R 4.1.2)             
##  yaml          2.2.1      2020-02-01 [1] CRAN (R 4.1.0)             
## 
## [1] /home/steffi/R/x86_64-pc-linux-gnu-library/4.1
## [2] /usr/local/lib/R/site-library
## [3] /usr/lib/R/site-library
## [4] /usr/lib/R/library
```

编辑后的文档将包括你全部工作流的信息。



你也可以结合 `print()` 命令，让操作更灵活，并且可以输出不同的格式：“text”, “Bibtex”, “citation”, “html”, “latex”, “textVersion”, “R”。

不过这样操作并不能导出版本号。

```r
print(citation("weathercan"), style = "text")
## LaZerte S, Albers S (2018). "weathercan: Download and format weather
## data from Environment and Climate Change Canada." _The Journal of Open
## Source Software_, *3*(22), 571. <URL:
## https://joss.theoj.org/papers/10.21105/joss.00571>.
```

或者如下，可以批量导出特定包信息：

```r
library(purrr)

c("weathercan", "magick", "tidyhydat") %>%
  map(citation) %>%
  print(style = "text")
## [[1]]
## LaZerte S, Albers S (2018). "weathercan: Download and format weather
## data from Environment and Climate Change Canada." _The Journal of Open
## Source Software_, *3*(22), 571. <URL:
## https://joss.theoj.org/papers/10.21105/joss.00571>.
## 
## [[2]]
## Ooms J (2021). _magick: Advanced Graphics and Image-Processing in R_. R
## package version 2.7.3, <URL:
## https://CRAN.R-project.org/package=magick>.
## 
## [[3]]
## Albers S (2017). "tidyhydat: Extract and Tidy Canadian Hydrometric
## Data." _The Journal of Open Source Software_, *2*(20). doi:
## 10.21105/joss.00511 (URL: https://doi.org/10.21105/joss.00511), <URL:
## http://dx.doi.org/10.21105/joss.00511>.
```

最后推荐使用[grateful](https://github.com/Pakillo/grateful)包，`cite_packages()`指令也能完成引用信息的收集和整理，并且可以导出不同的格式：Word document, PDF file, markdown file, or Rmarkdown file.

## 高阶技能

如果你期望你的项目不仅是可重复的，还是可复现的，那么可以使用R包`renv`或者版本控制器`Docker containers `。

> This article was first published on **[rOpenSci - open tools for open science](https://ropensci.org/blog/2021/11/16/how-to-cite-r-and-r-packages/)**, Zhaoyu has translated this English article and quotes it here.
