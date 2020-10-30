---
# Documentation: https://sourcethemes.com/academic/docs/managing-content/

title: "One- or Two-Sided Test"
subtitle: ""
summary: ""
authors: [Shuguang Sun]
tags: [pvalue]
categories: [statistics]
date: 2020-10-02T17:26:36+08:00
lastmod: 2020-10-02T17:26:36+08:00
featured: false
draft: fasle

# Featured image
# To use, add an image named `featured.jpg/png` to your page's folder.
# Focal points: Smart, Center, TopLeft, Top, TopRight, Left, Right, BottomLeft, Bottom, BottomRight.
image:
  caption: ""
  focal_point: ""
  preview_only: false

math: true

# Projects (optional).
#   Associate this post with one or more of your projects.
#   Simply enter your project's folder or file name without extension.
#   E.g. `projects = ["internal-project"]` references `content/project/deep-learning/index.md`.
#   Otherwise, set `projects = []`.
projects: []
---


## 问题：One- or Two-Sided Test?

Two-Sided Test 的简单形式 $H_0: \theta_1 = \theta_2$ v.s. $H_1: \theta_1 \neq \theta_2$，其检验的是参数是否为零，比如列联表中两治疗组见否有差异 (Row Mean Scores)，是否相关(Nonzero Correlation)，是否有关系 (General Association)等。按照常例，会将Two-Sided Test 的 p-value 与显著性水平（通常 $\alpha = 0.05$）进行比较，从而得到统计学结论。如果没有特别说明，我们看到的显著性水平 $\alpha = 0.05$ 都是指双侧的。

One-Sided Test 的简单形式 $H_0: \theta_1 = \theta_2$ v.s. $H_1: \theta_1 > \theta_2$ 或者 $H_0: \theta_1 = \theta_2$ v.s. $H_1: \theta_1 < \theta_2$，其备择设有方向性，例如“无效” v.s. “有效”，或者有顺序的备择假设（组1 < 组2 < 组3）。单侧检验看起来更符合药物研发的很多场合，即“无效” v.s. “有效”（如果劣效，一步步淘汰，无法注册上市）。一个自然的问题：One-Sided Test 对应显著性水平是多少？相应的 单侧 p-value 继续与 $\alpha = 0.05$ 进行比较，还是与 $\alpha = 0.025$？如果是后者似乎很吃亏，Odds 都是二十分之一，为什么要为不感兴趣的“劣效”付出代价？比如Koch和Billings (1988^[^1]) 证明在正态假设下，当显著性水平为5%，把握度为80%和90%, 双侧检验和单侧检验所需要的样本量分别增长27%和23%，虽然样本量只增加了大约 1/4，但是成本（时间、人力、金钱等各方面）会显著增加。

## 回答：ICH E9

> It is important to clarify whether one- or two-sided tests of statistical
> significance will be used, and in particular to justify prospectively the use
> of one-sided tests. If hypothesis tests are not considered appropriate, then
> the alternative process for arriving at statistical conclusions should be
> given. The issue of one-sided or two-sided approaches to inference is
> controversial and a diversity of views can be found in the statistical
> literature. The approach of setting type I errors for one-sided tests at half
> the conventional type I error used in two-sided tests is preferable in
> regulatory settings. This promotes consistency with the two-sided confidence
> intervals that are generally appropriate for estimating the possible size of
> the difference between two treatments.

曾经战斗力为 5 的我，天真的以为单边检验的 p-value 可以跟 $\alpha = 0.05$ 进行比较，就被现实教育了。


## 与α有关的讨论

正如ICH E9所指出的，关于使用单侧方法还是使用双侧方法的讨论由来已久。其中最广泛的讨论是，为什么不用0.05下的单侧检验。虽然已有结论，但了解讨论的观点和论据也很有用处。

Georgi Z. Georgiev（<Statistical Methods in Online A/B Testing>的作者）的[Onesided.org](https://www.onesided.org/)。网站给出了很多文章和[文献](https://www.onesided.org/literature/)（包括For one-sided statistical tests，Against one-sided statistical tests和Regulatory guidelines等），可以作为一个起点---虽然我不认同其中的一些观点或例子。其中几篇文章是对历史的回顾，比如[Fisher, Neyman & Pearson: Advocates for One-Sided Tests and Confidence Intervals](https://www.onesided.org/articles/fisher-neyman-pearson-advocates-one-sided-tests-confidence-intervals.php)，包括了Fisher和Neyman对one-sided vs two-sided tests的一些态度。另外[Reasons for misunderstanding and misapplication of one-sided tests](https://www.onesided.org/articles/reasons-for-misunderstanding-and-misapplication-of-one-sided-tests.php)也是一个汇总。


Peace, K. E. (1991[^2]) 汇总了ASA 1990年年会一个Session的讨论，最终作者认为

> "Whether a one-sided or a two-sided p value should be used for reporting the results of an analysis should be determined by the a priori question the investigation seeks to answer. It is concluded that one-sided p values are appropriate in clinical trials whose objective is to provide definitive, confirmatory evidence of efficacy of pharmaceutical compounds."

文中也指出反方的一个观点 

> "Some individuals with whom I've spoken about the one-sided or two-sided p-value issue, use in support of two-sided p values the fact that one does not know at the outset whether drug will be superior or inferior to placebo. And if the trial is conducted with a one-sided alternative that reflects superiority of the drug, and it turns out that when the trial is conducted, placebo is numerically better than the drug, one cannot say anything about such an event."

同时也指出，I类错误通常被认为是 "**regulatory risk**" 或 "**consumer's risk**"，而II类错误通常被认为是 "drug sponsor's risk"，监管部门接受双侧5%的regulatory risk，实际上是单侧2.5%.

> There should be consistency between sidedness of the regulatory or consumer's risk and the design of definitive proof of efficacy trials to be submitted to support the application. For regulatory authorities to operate on a two-sided 5% regulatory risk is in fact operating on a 2.5% level. Regulatory authorities are free to choose the consumer risk level. Personally, I would much prefer such a risk to be 2.5%, and one-sided tests adopted for the efficacy requirement, than what is currently the practice.

（报告中提供单侧 p value，而不是双侧 p value）

Fisher, L. D. (1991[^3])的落脚点更多是与placebo control的研究，指出一种情况在美国注册有可能要求两个阳性研究，这种情况下单侧 0.05是否更合适。

> As an FDA physician once said, the level of proof needed is not the 1 in 20 of the null hypothesis in one trial at the 0.05 level, but rather 1 in 20 squared, or 1 in 400. In actuality both trials need to reject the null hypothesis in the correct direction. Thus with two-sided tests one is working at the 1 in 1600 level for the approval of a drug. This seems a rather rigorous level of proof.

两个独立阳性研究要求更多是为了避免意外。


1. In a situation where at least two positive placebo-controlled trials are needed, one-sided tests are the appropriate model.

作者认为，对于一些存在较大不确定性的研究，比如非典型患者等，“Mysterious things can happen in one study”，所以认可需要两个研究、1/400，认为单侧检验就够了.

2. When only one placebo-controlled trial may ethically be performed if the result is positive the amount of evidence required is of more concern and the answer is not as clear cut. I lean toward one-sided trials at the 0.05 significance level if the preliminary evidence and biological understanding are firm; otherwise, a significance level of 0.025 is appropriate.

作者在讨论中，还是强调了各方面的支持性证据是否足够强。

3. For active control trials there is usually sponsor and regulatory interest if the new compound is better than the active control --- and the sponsor will wish to use this fact in marketing if it is true. Here two-sided trials seem most appropriate.

（现实是都是双侧 0.05 或者单侧 0.025）

Moyé和Tita (2002[^4]) 更认可双侧检验，

> We argue here, however, that one-tailed testing should be avoided in healthcare research for ethical and cost-efficiency reasons, especially in randomized trials in which the investigator controls the intervention. Rather than reflecting the investigators' a priori intuition, the type I error should reflect the uncertainty of the research effort's future conclusions. This is critical in a field in which healthcare practitioners and healthcare researchers can inadvertently do harm to their patients.

作者认为单侧检验并不能够减少总体样本量。单侧0.05的证据等级较低，从伦理上和科学上可能需要其的重现性 --- 也就是说需要两个独立的阳性研究，这样反而需要更多的样本量。

> Such a two-tailed study requires only 63% of the requisite total sample size for 2 separate one-sided studies, everything else being equal...

另外一点与Peace, K. E. (1991[^2])中的一点类似，如果最终结果的方向与单侧假设的备择方向相反怎么解释？这样的研究能提供什么信息？

Ruxton, G. D.和Neuhäuser, M. (2010[^5]) 给出了一些何时使用单侧检验的意见：

1. Although one‐tailed hypothesis tests are commonly used, clear justification for why this approach is used is often missing from published papers.

2. Here we suggest explicit questions authors should ask of themselves when deciding whether or not to adopt one‐tailed tests.

3. First, we suggest that authors should only use a one‐tailed test if they can explain why they are more interested in an effect in one direction and not the other.

4. We suggest a further requirement that adoption of one‐tailed testing requires an explanation why the authors would treat a large observed difference in the unexpected direction no differently from a difference in the expected direction that was not strong enough to justify rejection of the null hypothesis.

5. These justifications should be included in published works that use one‐tailed tests, allowing editors, reviewers and readers the ability to evaluate the appropriateness of the adoption of one‐tailed testing.

6. We feel that adherence to our suggestions will allow authors to use one‐tailed tests more appropriately, and readers to form their own opinion about such appropriateness when one‐tailed tests are used.

## 统计量

检验统计量与p value也有关系，比如$\chi^2$、$F$统计量，对应的p value本身是单侧的（即大于等于统计量的值的概率），但是检验却可能是双侧的（即等与不等、是与不是等），比如列联表的卡方检验和组间比例的差值、RR、OR等。分布之间有关系，比如正态分布变量的平方服从自由度为1的卡方分布；不同的检验统计量之间有互通的关系，比如某些模型下边的似然比检验的渐近卡方统计量与系数的渐近正态统计量。所以单侧还是双侧跟所用的统计量也有关系，这也是为什么很多讨论集中在疗效，也有些例子里是HR。

Adaptive Design方法中需要多次分析结果的合并，有基于p value的，也有基于统计量的，比如Group Sequential，需要知道多次分析的统计量之间的联合分布。如果是基于正太统计量的分析，在认可双侧5%或单侧2.5%的水平的基础上，一般而言，选择双侧检验还是单侧检验，样本量是相同的。

## Reference

[^1]: Koch, G. C., Gillings, D. B. (1988). Tests, one-sided versus two-sided. In: Encyclopedia of Statistical Sciences, 9, 218-222.. Wiley, New York, 

[^2]: Peace, K. E. (1991). One-sided or two-sided p values: which most appropriately address the question of drug efficacy? Journal of Biopharmaceutical Statistics, 1(1), 133–138. http://dx.doi.org/10.1080/10543409108835010

[^3]: Fisher, L. D. (1991). The use of one-sided tests in drug trials: an FDA advisory committee member's perspective. Journal of Biopharmaceutical Statistics, 1(1), 151–156. http://dx.doi.org/10.1080/10543409108835012

[^4]: Lemuel A. Moyé, & Tita, A. T. (2002). Defending the rationale for the two-tailed test in clinical research. Circulation, 105(25), 3062–3065. http://dx.doi.org/10.1161/01.CIR.0000018283.15527.97

[^5]: Ruxton, G. D., & Neuhäuser, M. (2010). When should we use one-tailed hypothesis testing? Methods in Ecology and Evolution, 1(2), 114–117. http://dx.doi.org/10.1111/j.2041-210X.2010.00014.x
