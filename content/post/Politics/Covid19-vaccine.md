---
# Documentation: https://sourcethemes.com/academic/docs/managing-content/

title: "Covid-19 Vaccines Development"
subtitle: ""
summary: ""
authors: [Shuguang Sun]
tags: [politics]
categories: [politics]
date: 2020-09-01T19:23:53+08:00
lastmod: 2020-09-03T22:35:04+08:00
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

## 引言

2019年底突如其来的疫情，持续时间长，影响范围广，带来了各种层面的影响。

## 疫苗开发面临的挑战和要求

柳叶刀 (The Lancet) 发表了 Krause 等 (2020[^1]) 的文章，提出了三个问题，并进行了讨论：

(1) whether to demand not only proof of some vaccine efficacy but also proof of worthwhile efficacy;
(2) whether the initial trials of vaccine against placebo should prioritise not only single-vaccine trials but also a multivaccine trial; and
(3) whether to assess safety, protection against severe disease, and duration of protection by continuing blinded follow-up of the vaccine and placebo groups after definite evidence of short-term efficacy has emerged, but before an effective vaccine has been deployed locally in the general population.

从一个统计师的角度，认为大体讨论下边几点：

- 背景，很多很多新冠疫苗，当看到"很多"的时候自然会有多重比较的问题，如果标准低，疫苗效力很可能被高估，多撒几次骰子，总能出个豹子。而面对政治和经济方面的压力，会有更多的可能让本来效力不够高的疫苗上市。

- 非劣效：这是非劣效经典的梗。一旦出了一个或几个成为事实标准，以后的需要跟他们做对比，要么优效--令人止步的样本量，要么非劣效--可能让效果不那么好的疫苗上市，当它成为对照的时候，下一个更加弱的疫苗就有可能跟进，以至无穷，就没效了

考虑到控制病毒的严峻形势，让一些效力不高的疫苗上市，可能带来很大的破坏性，

- 所以要多个疫苗交叉比。文中提到了 WHO Solidarity Vaccines Trial，看起来像一个平台研究，需要用到适应性设计 (Adaptive Design)，包括疫苗选择，对照的改变（当有疫苗上市后，安慰剂可能不适合作为对照组）等等

- 所以要有"价值"--大体就是说不能仅仅统计显著，还要有临床意义，更遑论那些连统计性都没达到的

该文的参考文献，对于那些想深入了解 WHO, USA FDA, 及各路专家观点的人，也是一个很好的列表。

## 政治对医药/疫苗开发的影响

实际上政治对医药研发的影响经常发过，只是作为像我这样的小白没有注意到，例如 Avorn (2020[^2]) 提到的

> If the FDA declined to issue an October EUA for a COVID-19 vaccine, the agency could conceivably be directed to do so by the secretary of Health and Human Services, or possibly by the president. Such political intervention occurred in 2011, when the secretary of Health and Human Services reversed an FDA commissioner's decision to make the "morning after" contraceptive pill available over the counter to patients of all ages.

这里提到的是 2011 年美国卫生部历史上首次否决药监局的的决议，拒绝一种叫"单次B计划" (Plan B One-Step) 的紧急避孕药作为非处方药上市。

> For the first time ever, the Health and Human Services secretary publicly overruled the Food and Drug Administration, refusing Wednesday to allow emergency contraceptives to be sold over the counter, including to young teenagers. The decision avoided what could have been a bruising political battle over parental control and contraception during a presidential election season.[^3]

直到 2013 年美国法院裁决取消了该限制。同时引发了政府是否可以以安全性和有效性之外的理由拒绝一款药物的上市的讨论。

> A federal judge on Friday ordered that the most common morning-after pill be made available over the counter for all ages, instead of requiring a prescription for girls 16 and younger. But his acidly worded decision raises a broader question about whether a cabinet secretary can decide on a drug's availability for reasons other than its safety and effectiveness.[^4]

例如 Wood 等 (2012[^5]) 就是这类的讨论。


## Reference

[^1]: Krause, P., Fleming, T. R., Longini, I., Henao-Restrepo, A. M., Peto, R.,
  Dean, N. E., Halloran, M. E., ... (2020). Covid-19 vaccine trials should seek
  worthwhile efficacy. The Lancet, (), .
  http://dx.doi.org/10.1016/S0140-6736(20)31821-3

[^2]: Avorn, J., & Kesselheim, A. (2020). Regulatory decision-making on covid-19
  vaccines during a public health emergency. JAMA, (), .
  http://dx.doi.org/10.1001/jama.2020.17101

[^3]: Harris, Gardiner. Plan to Widen Availability of Morning-After Pill Is Rejected. The New York Times. 2011.
  https://www.nytimes.com/2011/12/08/health/policy/sebelius-overrules-fda-on-freer-sale-of-emergency-contraceptives.html

[^4]: Belluck, Pam. Judge Strikes Down Age Limits on Morning-After Pill. The New York Times. 2013.
  https://www.nytimes.com/2013/04/06/health/judge-orders-fda-to-make-morning-after-pill-available-over-the-counter-for-all-ages.html

[^5]: Wood, A. J., Drazen, J. M., & Greene, M. F. (2012). The politics of emergency
  contraception. New England Journal of Medicine, 366(2), 101–102.
  http://dx.doi.org/10.1056/NEJMp1114439
