---
# Documentation: https://sourcethemes.com/academic/docs/managing-content/

title: "p value and the 5% level"
subtitle: ""
summary: ""
authors: [Shuguang Sun]
tags: [pvalue]
categories: [statitics]
date: 2020-05-19T18:24:26+08:00
lastmod: 2020-05-19T14:43:17+08:00
featured: false
draft: false

# Featured image
# To use, add an image named `featured.jpg/png` to your page's folder.
# Focal points: Smart, Center, TopLeft, Top, TopRight, Left, Right, BottomLeft, Bottom, BottomRight.
image:
  caption: ""
  focal_point: ""
  preview_only: false

# Projects (optional).
#   Associate this post with one or more of your projects.
#   Simply enter your project's folder or file name without extension.
#   E.g. `projects = ["internal-project"]` references `content/project/deep-learning/index.md`.
#   Otherwise, set `projects = []`.
projects: []
---

## 火箭与马屁股

在回答火箭与马屁股的关系时，有个"马屁股决定说"：火箭的部件由铁路运输；在设计之初，火车轨道的宽度沿用了马车的轮宽标准；马车的轮宽由老路上上的辙迹决定；而辙迹来源于罗马的战车，马拉战车。所以马屁股在一定时期来决定了火箭的运力。

这是一种"路径依赖"理论。

## Fisher and 5% level

在早期，没有 5% 置信水平这个概念，各家采用各种界值。

Stigler (2008[^1]) 考证了早期统计学的文献，认为 R. A. Fisher 在引入 5% 这一水平的过程中起了主要作用。Fisher 在其 1925 年的书[^2]中需要用到一些分布表，即不同概率水平对应的统计量的值，比如正态分布表，可以提供 p = .01 到 .99 (间隔 .01) 以及 p = .001, .0001, ... 直至 .000000001，还有 t 分布表，是自由度 df = 1, 2, ..., 30, ∞ 和 p = .9, .8, .7, .6, .5, .4, .3, .2, .1, .05, .02, .01 的交叉表。而对于 F 分布，两个自由度，要想和正态或 t 分布表那样齐全，篇幅会非常非常大，所以 Fisher 在 1925 版的书里只提供了在不同自由度下 p = .05 对应的分布表。之后，在该书的第 3 版又增加了 p = 0.1 对应的分布表。1938 年的书[^3]里又进一步的扩展到了 20% 至 0.1%。

想象一下，当我们做（协）方差分析 ANOVA 的时候，手头只有一本 Fisher 1925 年的书，除了 5% 还有别的什么选择？

为什么可以接受 5%? 忽略历史原因，20 里边出 1 个的优势 (Odds)，已经可以满足很多决策中的不确定性需求了。更何况，我们开始学数数的时候大都是从掰着 5 个手指头开始的，相对于 4 或者 6，更容易接受 5 一些。

## HA and 5% level

p-value ≤ 5% 是一个实际上的金标准，但是现实中 p = 0.05 并不是一个 "pass/fail" 的必备标准。抛开那些 Rare Disease 或桥接试验，也有一些例子中 p > 0.05 依然获得上市批准，比如 FDA 在 2017 年批准了 Portola 的 Bevyxxa。

该批准基于 APEX 这一入组 7,500 人的关键性研究。它由 3 个队列组成：

- Cohort 1: D-dimer of 2 times the ULN or more

- Cohort 2: D-dimer of 2 times the ULN or more plus all patients age ≥75 years

- Cohort 3: Overall study population, all eligible patients

方案中规定了顺序检验方法：首先检验 Cohort 1；如果 Cohort 1 成功，才能检验 Cohort 2；Cohort 2 成功才能检验 Cohort 3。其结果是有争议的，在 Cohort 1 中 p-value 仅有 0.054 > 0.05，按理应该停止假设检验过程，在 5% 的水平下，Betrixiban 没有显著的比 Lovenox 优效。

Portola 基于 APEX 的整体结果，不算差的有效性数据 ("探索性分析"显示，Cohort 2 的 p-value 为 0.029，Cohort 3 总体人群的 p-value 为 0.006) ，较好的安全性，提交了注册申请，而最终也获得上市批准[^4] [^5].

|                                             |    RR | P value |
|---------------------------------------------|-------|---------|
| Cohort 1: Elevated D-Dimer                  | 0.806 |   0.054 |
| Cohort 2: Elevated D-dimer or age ≥75 years | 0.800 |   0.029 |
| Overall study population                    | 0.760 |   0.006 |

## 是否还需要 5%?

关于是否需要 5% 作为标准有很多争论。其中一种声音说：如果连 p-value 小于 5% 都不想达到，那还对要研发的药物有什么信心？特别是当我们在计划试验的时候。回想一下，对 5% 的质疑很多出自 1. 样本量太大想减小的时候，而样本量大有部分原因是因为预期的效应量就不大 2. 试验结果出来，p-value 比 0.05 大那么一点的时候。

归根结底，我们需要对证据的说服力进行评价。我很喜欢 "统计性" 这个说法，而不仅仅是一个数字。

## ASA 关于 p-value 的六个原则

ASA (Wasserstein 2016[^6]) 关于 p-value 提出了 6 个 principles:

1. P-values can indicate how incompatible the data are with a specified statistical model. 

2. P-values do not measure the probability that the studied hypothesis is true, or the probability that the data were produced by random chance alone. 

3. Scientific conclusions and business or policy decisions should not be based only on whether a p-value passes a specific threshold. 

4. Proper inference requires full reporting and transparency. 

5. A p-value, or statistical significance, does not measure the size of an effect or the importance of a result. 

6. By itself, a p-value does not provide a good measure of evidence regarding a model or hypothesis.

"Well-reasoned statistical arguments contain much more than the value of a single number and whether that number exceeds an arbitrary threshold. The ASA statement is intended to steer research into a 'post p<0.05 era.'"

以及

Good statistical practice is an essential component of good scientific practice, the statement observes, and such practice "emphasizes principles of good study design and conduct, a variety of numerical and graphical summaries of data, understanding of the phenomenon under study, interpretation of results in context, complete reporting and proper logical and quantitative understanding of what data summaries mean."



[^1]: Stigler, S. (2008). Fisher and the 5% level. CHANCE, 21(4), 12-12. http://dx.doi.org/10.1007/s00144-008-0033-3

[^2]: Fisher, Ronald A. (1925). Statistical Methods for Research Workers (first ed.), Edinburgh: Oliver & Boyd.

[^3]: Fisher, Ronald A., and Yates, Francis (1938). Statistical Tables for Biological, Agricultural and Medical Research (first ed.), London: Oliver & Boyd.

[^4]: FDA (2017). https://www.fda.gov/drugs/resources-information-approved-drugs/fda-approved-betrixaban-bevyxxa-portola-prophylaxis-venous-thromboembolism-vte-adult-patients

[^5]: Oregon State University and Oregon Health Authority (2017). New Drug Evaluation: Betrixaban Capsules. https://www.orpdl.org/durm/meetings/meetingdocs/2017_11_30/finals/Betrixaban_NDE.pdf

[^6]: Wasserstein, R. L., & Lazar, N. A. (2016). The ASA statement on p-values: context, process, and purpose. The American Statistician, 70(2), 129-133. http://dx.doi.org/10.1080/00031305.2016.1154108
