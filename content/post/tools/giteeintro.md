---
# Documentation: https://sourcethemes.com/academic/docs/managing-content/

title: "Gitee 与 Git：个人用户也有需求"
subtitle: ""
summary: ""
authors: [Shuguang Sun]
tags: [gitee, git, github]
categories: [tools]
date: 2020-09-06T13:45:17+08:00
lastmod: 2020-09-06T13:45:17+08:00
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

## 什么是 [Gitee](https://gitee.com/)

Gitee 是国内一个云端软件开发协作平台，是基于 Git 的托管平台，类似于
[github](https://github.com/)。2020年7月14日，工信部公布了“2020 年开源托管平台项目结果”，
选定依托“码云 Gitee” 建设中国独立的开源托管平台（[工信部携码云 Gitee 入场，国内
开源生态建设进入快车道](https://blog.gitee.com/2020/08/17/gitee-gxb/)）。

目前，Gitee 对个人免费，可以免费使用总计 5G 私有仓库。

## 为什么个人用户需要 Gitee 这类协作/托管平台

大多数公司有自己的文档管理平台，所以这里只说个人事务。

作为一个计算机老用户，从接触之初就被灌输了“勤做备份”的观念 --- 否则分分钟有“血泪”的教训。于是可以给文件加后缀，日期的，“vX”的，各种各样，如果不是“断舍离”这样精于文件管理的最后就会迷失在众多版本文件中。所以有个好的版本控制系统很不错，而有个稳定的服务器提供版本控制更不错。于是就逐渐接触了 github, gitlab, bitbucket, 然后现在的 gitee。

比如，个人笔记、随笔什么的就可以托管到私有账户（风险自负）。但是，和别的版本控制系统类似，其对非文本文件（如word, ppt）等的支持不是很友好，这类文件体积较大，占空间。如果想得到更好的支持，只能付费，或者变成企业用户。

协作，对个人用户私用的作用不大，但是对于团队，或者公开的项目是必不可少的。有些私人工具，将代码发不出来，说不定就有同好来进行更新---某 3-stars 项目作者的初感触。前公司自建了内部的 github，也是不错的形式，分享交流，即可以增加自己的影响力，也可以提高代码的利用率，还可以找 bug。


## 鸡蛋不放一个篮子里

使用过校友录、免费博客的都知道，免费平台有一些风险，比如突然关门。而另一方面，github 顺应美国政府要求，没有任何预先通知的情况下关停很多账号，将托管风险进一步的暴露出来。

将鸡蛋放入多个篮子里，同一个仓库可以镜像到不同的平台，操作上也不是很难。

速度也是一个需要考虑的问题，比如国内访问 github，网速就比较慢，gitee 的访问速度就很流畅。


## 如何使用 git

无论是 github, 还是 gitee, 都是基于 git 的托管平台。关于 git 的介绍网上很多，比如[Git 大全](https://gitee.com/all-about-git)等。不喜欢命令行工具的，也有很多客户端可以选择。
