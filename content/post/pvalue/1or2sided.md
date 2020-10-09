---
# Documentation: https://sourcethemes.com/academic/docs/managing-content/

title: "One- or Two-Sided Test"
subtitle: ""
summary: ""
authors: [Shuguang Sun]
tags: [pvalue]
categories: [statitics]
date: 2020-10-02T17:26:36+08:00
lastmod: 2020-10-02T17:26:36+08:00
featured: false
draft: true

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


## 


## ICH E9

"It is important to clarify whether one- or two-sided tests of statistical
significance will be used, and in particular to justify prospectively the use of
one-sided tests. If hypothesis tests are not considered appropriate, then the
alternative process for arriving at statistical conclusions should be given. The
issue of one-sided or two-sided approaches to inference is controversial and a
diversity of views can be found in the statistical literature. The approach of
setting type I errors for one-sided tests at half the conventional type I error
used in two-sided tests is preferable in regulatory settings. This promotes
consistency with the two-sided confidence intervals that are generally
appropriate for estimating the possible size of the difference between two
treatments."


https://www.invespcro.com/blog/one-tailed-vs-two-tailed-a-b-testing-everything-you-possibly-need-to-know/

https://blogs.oracle.com/marketingcloud/the-difference-between-one-tailed-two-tailed-testing

“If you’re running a test and only using a one-tailed test, you will only see significance if your new variant outperforms the default. There are 2 outcomes: the new variants win or we cannot distinguish it from the default.”

https://www.cliffsnotes.com/study-guides/statistics/principles-of-testing/one-and-twotailed-tests

“The decision of whether to use a one‐ or a two‐tailed test is important because a test statistic that falls in the region of rejection in a one‐tailed test may not do so in a two‐tailed test, even though both tests use the same probability level.”

“One-tailed test represents that the estimated test parameter is greater or less than the critical value. When the sample tested falls in the region of rejection, i.e. either left or right side, as the case may be, it leads to the acceptance of alternative hypothesis rather than the null hypothesis.”

Cons for one-tailed tests

Let’s assume that in reality \rho _{C}>\rho _{N} so the new design is worse than the current one. Then if you use the wrong direction of a one-tailed test (right- instead of left-sided), you will be not able to reject the null hypothesis that both designs are equally good.

If you would like to compute 95 percent confidence interval (95%CI) for the true difference between the two rates, note that in case of 1-sided test it is infinite from one side.

So for right-sided test 95%CI looks like [number, +∞) and (-∞, number] for the left-sided test.
Cons for two-tailed tests

When the conversion rate of the control and the conversion rate of the variation are not equal, but the difference between them is very small, you will not be able to detect this scenario since you “spend” all the power on both sides instead of one.

Let’s summarize the advantages and disadvantages of both methods:

Bad and good habits when it comes to one-tailed vs. two-tailed A/B tests

    Use a two-tailed test when you do not have a clue which one is a better approach for your specific situation.
    Do not conduct one after the other. If you are not able to reject the null hypothesis in 2-sided test (with less power) you will not be able to reject it with a one-tailed test (more power).
    Do not conduct 1-sided test after 2-sided. If you were able to reject the null in a two-tailed test you will be able to reject it in a one-tailed too (with the right side of the association chosen).
    Conduct a one-tailed test if your 2-tailed test was not enough powered.
    If you do not have a strong evidence that the new design is better than the current one use two-sided test to account for both possible: harmful and beneficial effects of a new design.
    Most software uses 2-sided tests but it is very easy to use them to conduct the one-sided test. In order to do it, it is enough to multiply your current significance level for the 2-sided test by 2\alpha. So, use\alphainstead of.


https://www.onesided.org/articles/the-paradox-of-one-sided-v-two-sided-tests-of-significance.php

The paradox of one-sided vs. two-sided tests of significance

How can one be less certain that there is any difference than that there is difference in a specified direction?

https://www.onesided.org/articles/widespread-usage-of-two-sided-tests-result-of-usability-issue.php
Is the widespread usage of two-sided tests a result of a usability/presentation issue?

In short, I believe that a significant reason for the preference for two-sided tests over one-sided ones is how the famous Fisher tables of the T-distribution, Z-distribution and X2 distribution were tabulated and presented.


https://www.onesided.org/articles/examples-of-improper-use-of-two-sided-hypotheses.php

Improper use of two-tailed tests in clinical and pharmacological trials

First, I present an example from a large breast-cancer trial (ALTTO): "Adjuvant Lapatinib and Trastuzumab for Early Human Epidermal Growth Factor Receptor 2–Positive Breast Cancer: Results From the Randomized Phase III Adjuvant Lapatinib and/or Trastuzumab Treatment Optimization Trial" by Piccart-Gebhart et al. (2016) [1]. The goals of the trial involving 8381 patients was to test the promising adjuvant Lapatinib (L) in combination with standard therapy with trastuzumab (T) for effects in improving outcomes for metastatic human epidermal growth factor 2-positive breast cancer.

Eyebrowes will certainly be raised when one reads that in planning the study "Sample size calculations focused on the two-sided superiority comparison between the L+T arm and the T arm". I thought "two-sided superiority" might have been a typing mistake, since it makes zero sense, but the authors are yet to respond to my inquiry into their paper. If it was not a typo, then I cannot fathom how a non-directional two-sided alternative can at the same time be a superiority (directional) one as well. This is far from the major issue, though.

The authors report that "In the ITT population, a 16% reduction in the hazard of a DFS event was observed with L+T compared with T, but this effect was modest, not statistically significant at .025, and of little clinical significance in consideration of the additional toxicity" and similarly make the conclusion that "Adjuvant treatment that includes L did not significantly improve DFS compared with T alone and added toxicity. One year of adjuvant T remains standard of care.".

However, despite making claims about reduction of the hazard ratio, the paper only presents two-sided confidence intervals at 97.5% (due to a correction for the three initial arms) while what should have been presented was a one-sided interval. Such an interval does exclude an HR of 1 (upper-bound of 0.98) making the result statistically significant. The reported p-value of 0.048 was also two-sided, while a one-sided p-value of 0.024 would have just passed the requirement for p < 0.025 (I actually get 0.017 using the same numbers, not sure why). Therefore the claim for a reduction in HR is in fact statistically significant, contrary to what the paper states.

Whether the up to ~45% reduction in the hazard ratio (lower bound of a one-sided 97.5% interval) is of substantive significance and whether it offsets the observed side effects is a different story, but the fact is that the L+T arm was in fact statistically significantly better than the T arm at the risk level adopted by the researchers and it should have been reported as such. Decision makers such as regulatory bodies, physicians and patients can then make up their own mind based on their particular circumstances and risk tolerance. However, this can hardly happen when the reported error estimate is not related to the claim and conclusion of the paper.


https://www.onesided.org/articles/refining-statistical-guidelines-requirements-one-sided-tests.php

Refining statistical guidelines and requirements for one-sided tests

he FDA does so in its "Statistical Guidance on Reporting Results from Studies Evaluating Diagnostic Tests" while the EMA outlines its recommendations in "Statistical Principles for Clinical Trials".

The FDA guidelines

The FDA guidelines [1] do not specify risk explicitly, but they do require the reporting of 95% two-sided intervals "FDA recommends you report measures of diagnostic accuracy (sensitivity and specificity pairs, positive and negative likelihood ratio pairs) or measures of agreement (percent positive agreement and percent negative agreement) and their two-sided 95 percent confidence intervals.". I’ve seen people draw from this that regulatory risk is set at 5% but given that a drug that is harmful or increases risk will never be approved the actual risk is 2.5% when the one-sided statistic corresponding to such claims is calculated. I believe it will be beneficial for all parties if it is expressed as such explicitly.

Doing so will encourage the reporting of one-sided tests where appropriate, meaning almost universally. The medical literature will finally be more at ease in reporting the error probability statistics that match its claims.
The EMA guidelines

The EMA guidelines [2] are more explicit as they state that "Conventionally the probability of type I error is set at 5% or less or as dictated by any adjustments made necessary for multiplicity considerations;". They are wise to continue this with "the precise choice may be influenced by the prior plausibility of the hypothesis under test and the desired impact of the results. [...] Alternative values to the conventional levels of type I and type II error may be acceptable or even preferable in some cases.". I read this as a clear acknowledgement that there is nothing special about the 5% boundary, which is a good thing.

Then we can read, regarding one-sided tests: "The approach of setting type I errors for one-sided tests at half the conventional type I error used in two-sided tests is preferable in regulatory settings." after stating that "It is important to clarify whether one- or two-sided tests of statistical significance will be used, and in particular to justify prospectively the use of one-sided tests."

The justification of using one-sided tests is not at all needed, as already discussed. The second sentence basically means that maximum regulatory risk is in fact set at 2.5% for claims of benefit, non-inferiority, equivalence, harm, increased or decreased risk, etc. same as the FDA’s.

My recommendation to EMA would be to make the maximum 2.5% risk explicit and clear and to drop the requirement for special justifications for using one-sided tests as none such precautions are needed. As we know, it is a myth that a one-sided test is somehow biased or would result in more false positives.
The EFSA guidelines

I’ve also looked at the EFSA (European Food Safety Authority) guidelines ("Guidance on Statistical Reporting") [3] and I did not find any hint of a universal regulatory risk minimum and barely anything about one-sided vs. two-sided tests:

"For estimation, the interval estimate to be used should be specified and justified (e.g. confidence or credible interval, level of probability, whether one- or two-sided).".

I think EFSA are erring on the cautious side here, but at least both one- and two-sided intervals are put on the same level of need for justification. I believe "justification" is too strong a word and I think so long as the null hypothesis is specified there is no need for any further justification. If the claim being supported is directional and of the same direction as the computed estimate there should be no issues and no need for explicit justification.
The EPA guidelines

The US Environmental Protection Agency (EPA) statistical guidebook is "Data Quality Assessment: Statistical Methods for Practitioners" [4]. It almost has the format of a textbook with formulas, examples, etc. They do not set any regulatory risk standards, but they mention that the levels 90%, 95% and 99% might be important for decisions makers.

The guideline contains clear endorsement of using one-sided tests and many examples of doing so using their very well laid out statistical tables. In fact, the only fault I could find with it was a poor attempt to provide an example for when a two-sided test was appropriate since such a test was put forward as supporting a clearly one-sided claim about the efficiency of a treatment for reducing contamination in an area.

I’m sure there are other guidelines in different agencies around the world that can be used as positive examples or as cases in which significant improvement can be achieved. It is certainly not within my interests to cover them all, but I believe the examples and brief notes given here would be helpful in writing better statistical guidelines.
References:

[1] US Food and Drug Administration (FDA): "Statistical Guidance on Reporting Results from Studies Evaluating Diagnostic Tests", drafted in 2003, issued on March 13, 2007.

[2] European Medicines Agency (EMA): "Statistical Principles for Clinical Trials", drafted 1997, issued Mar 1998.

[3] European Food Safety Authority (EFSA) (2014) "Guidance on Statistical Reporting", EFSA Journal 12(12):3908

[4] US Environmental Protection Agency (EPA) "Data quality assessment: statistical methods for practitioners", EPA QA/G-9S, issued Feb 2006


https://www.onesided.org/literature/
