---
# Documentation: https://sourcethemes.com/academic/docs/managing-content/

title: "新冠疫苗的有效性"
subtitle: ""
summary: ""
authors: [Shuguang Sun]
tags: []
categories: [Statistics, Vaccine]
date: 2020-12-21T21:20:15+08:00
lastmod: 2020-12-21T21:20:15+08:00
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

## 前言

上周五跟同学聚餐闲聊，说到疫苗的问题，有效率95%，有效率86%，对方开着玩笑说100人还是会有5个中招，感觉还是很恐怖的样子。

这种说法似乎很普遍，觉得有必要澄清一下。

观点：**疫苗有用，国家让打的时候就打。**

## 试验结果

BioNTech 和 Pfizer 开展的研究（ClinicalTrials.gov number, NCT04368728）表明疫苗 BNT162b2 两剂量方案的在16岁以上人群中对 Covid-19 的保护率达到 95%。Polack 等[^1]的文章对研究结果进行了报道。

其中有效性分析的计划：

> Analysis of the first primary efficacy end point included participants who received the vaccine or placebo as randomly assigned, had no evidence of infection within 7 days after the second dose, and had no major protocol deviations (the population that could be evaluated). Vaccine efficacy was estimated by 100 × (1 − IRR), where IRR is the calculated ratio of confirmed cases of Covid-19 illness per 1000 person-years of follow-up in the active vaccine group to the corresponding illness rate in the placebo group. The 95.0% credible interval for vaccine efficacy and the probability of vaccine efficacy greater than 30% were calculated with the use of a Bayesian beta-binomial model. The final analysis uses a success boundary of 98.6% for probability of vaccine efficacy greater than 30% to compensate for the interim analysis and to control the overall type 1 error rate at 2.5%.

- 关键词 1: Per 1000 person-years 每 1000 人年。是否感染 Covid-19 跟暴露时间有关系，时间越长累积的感染的可能性越高，所以要考虑随访时间，就有了“人年”的概念。发生率就是新发生的 Covid-19 例数除以总的人年。例如，治疗组在 2.214 个 1000人年里出现了 8 例 Covid-19，发生率是 3.6 每 1000 人年，也就是 1000 个人在一年里有大约 4 个人感染，而安慰剂组的发生率高达 72.9 每 1000 人年，也就是 1000 个人在一年里有大约 73 个人感染。

- 关键词 2: IRR (incident rate ratio)，是治疗组对安慰剂组中 Covid-19 发生率的比，3.6/72.9 x 100% = 5%，完成疫苗治疗方案并且前 7 天不感染之后的感染率仅为不接种的 **5%**!! 所以有效率，或者说保护率为 95%。


{{< figure src="/PoorStatistician/images/Vaccine/Polack2020_1.png" alt="Polack etc" >}}
来源：Polack 等[^1]

<!--
 !-- ![图片说明](/PoorStatistician/images/Vaccine/Polack2020_1.png)
 !-- 来源：Polack 等[^1]
  -->

## 95% v.s. 86%

我个人还是想等看到具体数据再作比较。从上文可以看到 IRR 是一个相对的指标，可以评价有效性。但是跨研究的比较就麻烦的多，例如人群是否相同，感染率是否相同，是否大样本等等。比如，安慰剂组的发生率是 73，那么其 5% 为 3.6，而如果安慰剂组的发生率是 60，那么其 5% 就是 3 了。在这么低的发生率下，35000 的样本量也不算“很大”。

疫苗有效率 95% 并不是说 100 个人里还有 5 个人可能被感染。从上边的数据看 1000 个人在一年里大约有 4 个人感染，12000 人在一个月里大约有 4 个感染，其实还可以安心...吧，虽然说这是美国、巴西和阿根廷那种形势下的发生率，但是治疗药物、治疗方法的开发上似乎还是不能放松。

安慰剂组的发生率，1000 个人在一年里大约有 73 个人感染，似乎不是很夸张的高？...美国是怎么一年里达到 1800 万，总人口的 5% 的？！或许是能够志愿参加研究的本身就有自我保护的意愿？做好防护，不要作。

更多亚组分析显示，完成第一剂之后的总发生率为 12.5 v.s. 69.1, 这比 3.6 v.s. 73 要差一些，治疗组的确诊病例大部发生在第一剂和第二剂之间，达到确认新冠总数的 78% (39/50)----似乎是因为那时候还有产生抗体，可以再找文献研究一下。

图总比文字更有说服力:

{{< figure src="/PoorStatistician/images/Vaccine/Polack2020_2.png" alt="" >}}
来源：Polack 等[^1]

## 参考文献

[^1] Polack, F. P., Thomas, S. J., Kitchin, N., Absalon, J., Gurtman, A., Lockhart,
  S., Perez, J. L., … (2020). Safety and Efficacy of the BNT162B2 mRNA Covid-19
  Vaccine. New England Journal of Medicine, 0(0), .
  https://dx.doi.org/10.1056/NEJMoa2034577
