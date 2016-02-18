---
layout: post
title: "轻松五步 极简建站"
comments: true
permalink: "first-post-on-cydog"
---
我用了2016年春节假期中的三天，学习了Markdown、Github和Jekyll等新技术，做了一个属于自己的极简博客网站，现在你可以访问[它](http://www.cydog.cn)了。在本文中，我将会一步步地教你：尽量不编程的情况下，如何来实现这个目标。

## 为什么要建个人博客网站
随着微信的蓬勃发展，很多人都有自己的微信公众号，但是有个人网站的还是少数。我相信拥有高质量的个人网站能够让你的能力得到进一步锻炼、形象得到进一步提升。

但是建个人博客网站整个过程的痛点比较多：
1. 建站平台比较难用，不管是Wordpress还是DedeCMS都有学习门槛
2. 网站开发好，上传到云主机上也比较费劲，不稳定、要花钱、不好更新等等
3. 最痛苦的是，要搞定多终端响应式页面需要很多前端技术（得懂编程）
所以很多人对此都望而却步了。虽然有类似Strikingly等免费的建站服务，但是稍微要多一些功能（比如独立域名）就要收费了。

## 我今天教你的方法可以轻松建站
这个轻松来自于我之前不断踩坑、再跳出来之后，总结出来的一些优秀做法。当然这也取决于你的技术熟悉度。是有一定技术含量，但你如能耐心跟着做的话，可以避免编程。通过改改内容，就可以搭建出自己的漂亮而免费的个人网站，还是很吸引人的。

我将会分为五个部分来介绍：
1. 前期准备
2. 在网上搭建网站
3. 在本地机上搭建网站并上传
4. 用极简风格来定制
5. 内容发布流程

## 一、前期准备
首先需要注册一个个人域名，可以在万网上申请，几十元一年的很低的费用。因为我们的网站将会在国外服务器上托管，所以不必做周期冗长的域名备案。其次在Github上申请一个账号、[学习下其用法](https://guides.github.com/activities/hello-world/)。如果对文本编辑工具（比如我用的Sublime Text等）和Markdown语言，做一些初步了解的话，有加分。

然后我建议用一个MacBook来做这个网站，因为我们用到的网站服务器是Jekyll。它本身是基于Ruby的，在Mac系统上的支持比较好。另外翻墙工具比如[Lantern](https://github.com/getlantern/lantern)也是必备的，因为很多技术问题在Google上一查就很清楚，比百度效果好多了。

## 二、在网上搭建网站系统
我们采用的是[Github Pages](https://pages.github.com/)系统来搭建网站。这个网站非常快速而稳定、在国内也可以访问、并且更妙的是托管完全**免费**。你可以按照Github Pages网站上说明，分三步来创建一个”个人或者组织的网站”

第一步在你的Github账号下创建一个叫username.github.io的库，注意这里的命名很*严格*，必须这个格式来。第二步，在库里创建一个CNAME文件，其中只有一行文字，就是你注册的那个网址，比如www.yoursite.com。第三步是到你的域名服务商（比如万网）那里做一个CNAME解析，来指向这个username.github.io。

这时候在这个库中，手工写个最简单的Hello World的index.html文件放进去。然后把你本机上的浏览器打开，访问www.yoursite.com，是不是能看到这个index.html上的内容了。是不是很有成就感？如果过程中遇到问题的话，可以查看这里的[帮助](https://help.github.com/categories/github-pages-basics/)。

## 三、在本地机上搭建网站系统并且上传
如果网站只是一个简单的HTML，那就太丑陋了，并且也不方便后期持续更新内容和做内容管理等等。所以一个叫[Jekyll](http://www.jekyllrb.com/)的大角色要上场了。这家伙的学名叫”静态页面生成器”。如果你听说过Wordpress的博客网站系统，那么我就告诉一点就行了：Jekyll等于是现代简约版的Wordpress系统。

我之前有过与Wordpress这个著名的网站系统打交道的体验，一句话**过于复杂**。不是专门学习和使用它的人，可是搞不定它。所以Jekyll，以百事可乐挑战可口可乐的姿态出现，成为我们年青一代的不二选择，呵呵。

在Mac上安装Jekyll不是一件容易的事，有三个坑等着你去跳。因为Jekyll官网上的醒目说明”好简单的安装啊”，是为了国外环境下的有技术背景的人准备的，说我还是建议你按照这个中国人写的如何安装的[博客文章](http://xiangxy.com/blog/mac%E4%B8%8Bjekyll%E7%9A%84%E5%AE%89%E8%A3%85%E4%B8%8E%E7%AE%80%E5%8D%95%E4%BD%BF%E7%94%A8/)来一步步安装，就不会踩到坑里挑不出来。我按照他说的方式，就安装成功了，感谢那个作者！

接着在本地机上，你安装一个Github的桌面客户端，把username.github.io的库给同步下来到本机上的一个文件夹。然后把Jekyll运行后产生的那个静态网站（在.site文件夹中），整个拷贝到这个库的文件夹中。再次打开Github桌面客户端，Commit所有的变化（即文件拷贝进去了），点击右上角的Sync按钮，就可以把本地机的网站上传到互联网上去。

再次在你的Mac或者手机上，打开浏览器，访问www.yoursite.com。乌拉，这次你能看到的是：由Jekylly在本地生成的那个静态网站了。路线跑通了，下面就是如何来定制该静态网站的事了。

## 四、定制化本地机的静态网站
这个定制化，分为知行合一两个方面。知是指从知识层面，武装起来对Jekyll的概念性认知，推荐其[官方文档](http://jekyllrb.com/docs/home/)来学习（说实话有点难懂）和国外某网友写的更浅显的[动手操作指南](http://jmcglone.com/guides/github-pages/)（比较推荐）。阅读这些文档，不在于掌握多少细节，在于熟悉起来Jekyll的整体概念。

从行的角度，代码细节最好还是用别人的改改来用。我从网上找到一篇很好的[用Jekyll建博客文章](http://joshualande.com/jekyll-github-pages-poole/)，比较喜欢他追求的极简风格和安装的插件功能。所以我在Github中找到了该作者的代码库，Folk（分支化复制）了一套到我自己的Github账号下。再通过Github桌面客户端同步到本地机上，然后打开那些代码文件，做了一些修改。

好消息是你不必做这些修改了，只要Folk我这个已经修改好的[代码库](https://github.com/jiansongy/jiansongy.github.io)到你自己的username.github.io的库里，就可以马上使用了。喔，也不是马上能用，还要在你本地机的命令行中运行sudo gem install来安装两个插件，因为作者用到了它们，分别叫jekyll-paginate和redcarpet。在命令行中，分别把这两个名字写到sudo gem install之后，进行运行即可。

## 五、内容发布流程
通过上面这些步骤，你在本地机上访问这个静态网站，就能看到我现在发布在我自己的www.cydog.cn的网站效果：
1、首页是最新的一篇博客文章的全文展示
2、上部有三个菜单项，分别是关于本站、文章清单、RSS订阅链接
3、底部有三个功能：向前或向后翻阅其他文章、进行Disqus评论和分享到Twitter
4、还有一个隐藏的功能是加入了Google Analytics的流量统计插件

接下来讲讲如何发布新的博客文章。你只要在本地机上的库中，在posts文件夹中，加入新的Markdown格式的文件即可做新文章发布，但要遵循下面三条。

首先在帖子的顶部加入一个Jekyll 称为Front Matter的内容，比如：
>layout: post
>title: “任意你想要写的文章标题”
>comments: true
>permalink: “title-of-this”

其次，把文件名称**严格**命名为: YYYY-MM-DD-title-of-this.md。这里的title-of-this不能出现重复现象。

最后，再通过我在第三步中讲过的，同步本地机文件夹，到你在网上的库username.github.io中去，就可以自动让你的网站显示出来这个新的帖子了，Jekyll会自动把各种细节都照顾好的，感谢Jekyll大侠。

# 后记
我就把这篇博客文章，放在我个人博客网站上，做为开业大喜的第一篇文章了，期待你在下面留言讨论互动。对于留言的朋友，为了便于你看清楚配置过程，我还提供了额外Bonus：本文章的思维导图版本，作为礼物附赠。谢谢！