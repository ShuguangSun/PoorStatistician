---
# Documentation: https://sourcethemes.com/academic/docs/managing-content/

title: "GNU/Linux - Manjaro"
subtitle: ""
summary: ""
authors: [Shuguang Sun]
tags: [linux]
categories: [Tools]
date: 2020-08-09T15:11:26+08:00
lastmod: 2020-08-09T15:30:26+08:00
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

## 用过的 Linux 发行版

VI 是一款非常古老经典的编辑器，几乎每一个发行版的 Linux 都会默认安装。Stackoverflow 上有个经典的问题：如何退出 VI, 在线等！ 

初步接触 Linux 是大学期间，学校机房，充满好奇的点进了 Linux 系统，后来忘记了，不知道是不是很快就按硬件的关机键了。自从研究生时有了自己的电脑，又开始了 Linux 的探索。首先用了 Debian，然后是 Debian 系的 Ubuntu，现在又转到 Arch Linux 系的发行版 Manjaro。

对于新手用户，我还是推荐 Ubuntu，有大厂支持，用户友好，基本上装完就可以用了，而且细节也照顾的不错。比如，R 在 Ubuntu 里可以自由的选用不同的 Blas 支持，无论是 R 自带的 Blas，还是 OpenBlas，Intel 的 MKL，都可以简单的设置一下就可以切换。用户需要操心的就比较少。

而我转到 Manjaro 主要两个原因，次要的原因是默认的 Ubuntu 比较大，启动稍微慢点，主要原因是软件更新太慢，不是 snapshot 的----对于尝鲜派来说，这当然很重要。疫情的 3 月，开启许久没有用的电脑，Manjaro 联网升级，结果中间断了一下网，而我又进行了一些神操作，系统崩溃了----这就是尝鲜的代价----只能重新安装了一遍 Manjaro。现在是基于 XFCE 的桌面，启动也变慢了----想快还是需要用轻量级的 i3.

## Manjaro 的安装

现在各个 Linux 的发行版几乎都一致：网上现在安装文件，烧到 USB 里建成自启动的安装盘，然后插入电脑安装。也就是装到 USB 里稍微麻烦点，一般的工具都需要管理员权限。

安装需要注意的事情有两个，一是联网，最好找一下国内的镜像，毕竟有些组件要升级话，国内网络更快；二是硬盘分区，MBR，系统区，用户区，最好提前规划一下。比如我一开始硬盘没分区，系统区和用户区在一起，3 月份重装的时候就抓瞎了，最为一个 Linux 小白，我都不知道怎么把用户区的数据备份出来...备份无论在什么地方都非常重要啊。

系统安装好基本就可以用了。需要的软件，也可以联网安装。或者是命令行，Debian 系的 apt，Arch 系的 pacman。如果不喜欢命令行，也有专门的图形界面的工具。

## Manjaro 的使用

我对自用机的需求比较简单，有 Emacs, R, python, 网络浏览器等就差不多了。当然对 GNU 以及更广泛的开源与不开源的世界来说，几乎就是用户有需求，就是实现----抛开好用不好用另说。

办公软件里也有不同的选择，Open/Free office，还有国产精品 WPS----没错，就是曾经将微软 Office 按在地上摩擦的 WPS。我是轻度的办公软件用户，对以上几个用的都不多，所以不做深入评论。

再一个是字体。随着互联网经济的蓬勃发展，字体也被随手解决了。Adobe 和 Google 合伙出来一套 CJK 字体，Adobe 叫思源，Google叫No豆腐。为什么说是与互联网经济有关呢？阿里也出了个普惠体，还有一个专门用于淘宝的字体----以前淘宝商铺好多广告因为字体原因被告侵权----于是就出一套字体解决了。

网络传言要在微信与Iphone之间二选一，这个还是比较简单的；而如果要在微信与Windows之间二选一呢？可惜腾讯对 Linux 的支持真的不给力，哪怕用 Wine 也需要花很多功夫。所以这是一个缺点。
