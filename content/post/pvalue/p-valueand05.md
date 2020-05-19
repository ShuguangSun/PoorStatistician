---
# Documentation: https://sourcethemes.com/academic/docs/managing-content/

title: "p value and the 5% level"
subtitle: ""
summary: ""
authors: [Shuguang Sun]
tags: [pvalue]
categories: [statitics]
date: 2020-05-19T11:24:26+08:00
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

“路径依赖”理论。

“马屁股决定说”。
　　这个说法认为：英国人发明了火车，而火车轨道的宽度在设计之初就沿用了马车的轮宽标准。
　　马车的轮宽是怎么确定的呢？
　　是根据英国老路上的辙迹确定的。当时路上辙迹的宽度是4.85英尺。
　　那么这些辙迹又是从何而来的呢？
　　你别着急呀，我正要说这个。这些辙迹是古罗马人定的。当时欧洲的长途老路都是由罗马人为他们的军队铺设的，罗马战车是他们的主要装备，4.85英尺正是罗马战车的宽度。

# Fisher and 5% level

Stigler[^1] 2008


[@Wasserstein2016]

Informally, a p-value is the probability under a specified statistical model that a statistical summary of the data (e.g., the sample mean difference between two compared groups) would be equal to or more extreme than its observed value.

The statement's six principles, many of which address misconceptions and misuse of the p-value, are the following: 

1. P-values can indicate how incompatible the data are with a specified statistical model. 
2. P-values do not measure the probability that the studied hypothesis is true, or the probability that the data were produced by random chance alone. 
3. Scientific conclusions and business or policy decisions should not be based only on whether a p-value passes a specific threshold. 
4. Proper inference requires full reporting and transparency. 
5. A p-value, or statistical significance, does not measure the size of an effect or the importance of a result. 
6. By itself, a p-value does not provide a good measure of evidence regarding a model or hypothesis.

The statement has short paragraphs elaborating on each principle.

Let me quote now from the ASA:

Well-reasoned statistical arguments contain much more than the value of a single number and whether that number exceeds an arbitrary threshold. The ASA statement is intended to steer research into a ‘post p<0.05 era.’

Further, an accompanying press release states:

Good statistical practice is an essential component of good scientific practice, the statement observes, and such practice “emphasizes principles of good study design and conduct, a variety of numerical and graphical summaries of data, understanding of the phenomenon under study, interpretation of results in context, complete reporting and proper logical and quantitative understanding of what data summaries mean.”


[^1]: Stigler, S. (2008). Fisher and the 5% level. CHANCE, 21(4), 12–12. http://dx.doi.org/10.1007/s00144-008-0033-3

[^2] Wasserstein, R. L., & Lazar, N. A. (2016). The ASA statement on p-values: context, process, and purpose. The American Statistician, 70(2), 129–133. http://dx.doi.org/10.1080/00031305.2016.1154108
