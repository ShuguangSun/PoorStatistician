---
# Documentation: https://sourcethemes.com/academic/docs/managing-content/

title: "随笔：DOR 与 DSN"
subtitle: ""
summary: ""
authors: [Shuguang Sun]
tags: [dor,methodology]
categories: [statitics]
date: 2020-10-09T11:31:24+08:00
lastmod: 2020-10-09T12:54:51+08:00
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

## Duration of Response

Duration of Response（DOR, 缓解持续时间），通常指从首次缓解（Response）至下一次
PD 或死亡的时间，通常在出现缓解的人群里进行分析，分析方法一般是生存分析的
Kaplan-Meier 方法。于是这里就出现一个问题：人群不是 ITT 的。

比如，McCaw 等[^1]就指出了 DOR 的结果是描述性的，有偏的，并且 DOR 的起点和删失时
间相关，所以以现在方法分析的 DOR 不是一个很好的终点。（文中提到了另外一种方法，
DOR = PFS - P/D/R event-free time）。

> The only signal potentially favoring nivolumab was from the duration of
> response (DOR),1 as underscored in the accompanying Editorial.2 The reported
> median DORs were 11.1 and 5.3 months for nivolumab and bevacizumab,
> respectively. However, this comparison might not be appropriate because these
> 2 medians were based on the DORs among responders only, and the objective
> response rates of the 2 treatment groups differed substantially: 7.8% for
> nivolumab vs 23.1% for bevacizumab.

同时 Weller 等[^2]给出了回应，ORR 是实体瘤领域的一个重要指标，但是在免疫治疗中可
能会有一些 potential false response, 因此描述性的 DOR 还是很有意义的；而如果不在
responder里分析，就会因为有太多零值而无法给出有效信息，等等。

这些都是讨论过很久的问题。但是最近看到另外的一个终点 DSN，两相对比就很有意思。

## Duration of Severe Neutropenia

Duration of Severe Neutropenia (DSN) 一般用于预防化疗引起的骨髓抑制的终点，通常
指从出现 ACN 到恢复的时间，但其分析人群是 ITT 或 mITT，而不是仅仅在出现 SN 的人
群中分析，分析方法一般是考察均值（方差）和中位数，例如 Blayney 等[^3]的
Plinabulin vs Pegfilgrastim 的研究。还没有看到 Blayney 等[^3]采用的比较方法，只
是看到“中位数”，就会自然的想到非参数秩方法，结合均值（方差）的统计量，可以比较零
值太多的数据的位置问题。

## DOR 与 DSN

统计是艺术，艺术存在冲突。DOR 与 DSN 就是一个冲突：两者都是 Duration，主要分析方
法并不相同。

DOR 是 ORR 的有力补充。从 DOR 被重视的时刻起，DOR 突出的就是“长”，越长越好，特别
是在 ORR 的差别不大，甚至稍微差一些的情况下（如 McCaw 等[^1]的例子）。其临床的解
释大体是，对于那些出现缓解的受试者，缓解会持续更长时间 --- 这当然是好的。从
Markov 过程的角度，DOR 考察的是从状态 R 到状态 P/D 的一个终点。从这个角度也许可
以不考虑零值（无缓解）。

DSN 并不是 SN 的补充，他本身就是一个主要终点。DSN 考察的是“短”，还有“位置”参数。
从预防骨髓抑制的角度，更多受试者没有发生 SN（即 DSN = 0），也预示着效果更好。所
以 DSN 考察的是发生 SN 和未发生 SN 的综合，其临床解释大体是，减少了 SN 的发生，
即使发生了SN，其持续时间也可能更短。

编剧和导演需要了解隐藏冲突背后的机制。


## Reference

[^1]: McCaw, Z. R., Tian, L., & Wei, L. (2020). Appropriate analysis of duration of
  response data in cancer trials. JAMA Oncology, (), .
  http://dx.doi.org/10.1001/jamaoncol.2020.4657

[^2]: Weller, M., Tatsuoka, K., & Reardon, D. A. (2020). Appropriate analysis of
  duration of response data in cancer trials-reply. JAMA Oncology, (), .
  http://dx.doi.org/10.1001/jamaoncol.2020.4664

[^3]: Blayney, D. W., Zhang, Q., Feng, J., Zhao, Y., Bondarenko, I., Vynnychenko,
  I., Kovalenko, N., … (2020). Efficacy of plinabulin vs pegfilgrastim for
  prevention of chemotherapy-induced neutropenia in adults with non-small cell
  lung cancer: a phase 2 randomized clinical trial. JAMA Oncology, (), .
  http://dx.doi.org/10.1001/jamaoncol.2020.4429
