
[TOC]

# 简介

这是一本介绍使用 Git 和 GitHub 的开源电子书，在线阅读地址：https://darrenliuwei.com/git-github-tutorial

本简介源码地址：https://github.com/zodensu/zodensu.github.io

阅读过程中若遇到语法错误、拼写错误、技术错误等等，不妨来个Pull Request或者Issues，这样可以帮助到其他阅读这本电子书的同学。

# GitHub介绍

[GitHub](https://github.com/) 是一家位于旧金山的公司，由 Chris Wanstrath、PJ Hyett 和 Tom Preston-Werner 三位开发者在2008年2月使用 [Ruby on Rails](http://rubyonrails.org/) 编写而成。

GitHub同时提供付费账户和免费账户。这两种账户都可以创建公开的代码仓库，但是付费账户还可以创建私有的代码仓库。

由于 [GitHub](https://github.com/) 在世界范围内具有非常非常大的影响力，导致 [GitHub](https://github.com/)  曾在中国、俄罗斯和印度等国被审查和封锁，虽然此网站是单纯的技术社区，一般不具政治敏感消息的特征，但相关代码可用于开发翻墙 [VPN](https://zh.wikipedia.org/zh-cn/%E8%99%9B%E6%93%AC%E7%A7%81%E4%BA%BA%E7%B6%B2%E8%B7%AF) 与反侦测等一系列在线隐蔽软件，而被许多法律设置严苛的政府盯上。

2015年8月，中国政府进一步收紧对互联网的控制。22日，翻墙软件 `Shadowsocks` 作者迫于警方压力删除项目。25日，翻墙软件 `GoAgent` 作者自行删除自己的代码。同一天 [GitHub](https://github.com/) 再次遭到来自中国大陆的 `DDoS` 攻击。部分开发者认为此次攻击与中国政府有关。


## 全球顶级科技公司纷纷加入 GitHub ，并贡献他们自己的项目代码

Google: https://github.com/google

Apple: https://github.com/apple

Facebook: https://github.com/facebook

Twitter：https://github.com/twitter

Microsoft：https://github.com/microsoft

Alibaba：https://github.com/alibaba
......

## 全球顶级开源项目都优先选择在 GitHub 上开源

Linux：https://github.com/torvalds/linux

Rails：https://github.com/rails/rails

Nodejs：https://github.com/nodejs/node

Ruby：https://github.com/ruby/ruby
......
## 全球顶级编程大牛加入GitHub

Linux 发明者 Linus Torvalds：https://github.com/torvalds
![Linux发明者](/img/Linux's-inventor.png)

其他就不一一列举了，GitHub 上活跃的很多是 Google 、Square、阿里等公司的员工，有些甚至还是Google Android Team组的，所以在这里你可以接触到全球顶级编程大牛！

## GitHub 有什么用

1. 学习优秀的开源项目
开源社区有一句流行的话叫不要重复发明轮子，某种意义上正是因为开源社区的贡献，我们的软件开发才能变得越来越容易，越来越快速。试想你在做项目时，如果每一个模块都要自己去写，如网络库、图片加载库、ORM库等等，自己写的好不好是一回事，时间与资源是很大的成本。对于大公司可能会有人力与资源去发明一套自己的轮子，但是对于大部分互联网创业公司来说时间是非常宝贵的。而且你在使用开源项目的过程也可以学习他们优秀的设计思想、实现方式，这是最好的学习资料，也是一份提升自己能力的绝佳方式！

2. 多人协作
如果你想发起一个项目，比如翻译一份不错的英文文档，觉得一个人的精力不够，所以你需要更多的人参与进来，这时候 GitHub 是你的最佳选择，感兴趣的人可以参与进来，利用业余时间对这个项目做贡献，然后可以互相审核、合并，简直不要太棒！

3. 搭建博客、个人网站或者公司官网
这个就不用多说了，现在越来越多的博客都是基于 GitHub Pages 来搭建的，你可以随心所欲的定制自己的样式，可以给你博客买个自己喜欢的域名，再也不用忍受各大博客网站的约束与各式各样的广告了！

4. 写作
如果你喜欢写作，而且基于 Markdown， 并准备出版书籍，那么推荐你用 Gitbook ，写作人的最爱！

5. 个人简历
如果你有一个活跃的 GitHub 账号，上面有自己不错的开源项目，还经常给别的开源项目提问题，Push 代码，那么你找工作将是一个非常大的优势，现在程序员的招聘很多公司都很看中你 GitHub 账号，某种意义上 GitHub 就可以算是你的简历了。而且不仅国内，很多国外的科技公司都会通过 GitHub 来寻找优秀的人才！

鸣谢参考：http://stormzhang.com/github/2016/05/25/learn-github-from-zero1

# GitHub基础知识

## Repository

仓库的意思，也就是你的项目。

## Issues

问题的意思。举个例子，别人发现你的项目中有 BUG，或者哪些地方做的不够好，他就可以给你提个 Issues ，然后你看到了这些问题就可以去逐个修复，修复好了就可以一个个的 Close。

## Star

收藏项目的意思。

## Fork

分叉的意思。你建立了一个项目，别人想在你这个项目的基础上做些改进，然后应用到自己的项目中，这个时候他就可以 Fork 你的项目，这时候他的 GitHub 主页上就多了一个项目，只不过这个项目是基于你的项目基础，他就可以随心所欲的去改进，但是丝毫不会影响原有项目的代码与结构。

## Pull Requests

发起请求的意思。这个其实是基于 Fork 的，还是上面那个例子，如果别人在你基础上做了改进，后来觉得改进的很不错，应该要把这些改进让更多的人受益，于是就想把自己的改进合并到原有项目里，这个时候他就可以发起一个 Pull Requests (简称PR)，原有项目的管理员就可以收到这个请求，这时候他会仔细 review 你的代码，并且测试觉得OK了，就会接受你的 Pull Requests，这时候你做的改进就会合并到原有项目里。

## Watch

关注的意思。如果你 Watch 了某个项目，那么以后只要这个项目有任何更新，你都会第一时间收到关于这个项目的通知提醒。

## Gist

代码片段的意思。有些时候你没有项目可以开源，只是单纯的想分享一些代码片段，那这个时候 Gist 就派上用场了。

鸣谢参考：http://stormzhang.com/github/2016/05/26/learn-github-from-zero2

# GitHub快捷键

在仓库主页上提供了快捷键方便快速导航。

* 按 t 键会打开一个文件浏览器
* 按 w 键会打开分支选择菜单
* 按 s 键会激活顶端的命令栏 (Command Bar)
* 按 y 键将会冻结这个页面，这样就算代码被修改了也不会影响你当前看到的
* 按 ? 键查看当前页面支持的快捷键列表 
![快捷键列表](/img/github's-fast key.png)

更多关于 GitHub 小知识请访问开源项目->[github-cheat-sheet
](https://github.com/tiimgreen/github-cheat-sheet)


# git介绍

[git](https://git-scm.com/)是一个分布式版本控制软件，由 [Linus Torvalds](https://en.wikipedia.org/wiki/Linus_Torvalds) 创作，于2005年以[GPL](https://en.wikipedia.org/wiki/GNU_General_Public_License)协议发布。最初目的是为更好地管理Linux内核开发而设计。

自2002年开始，Linus Torvalds 决定使用 [BitKeeper](https://en.wikipedia.org/wiki/BitKeeper)作为Linux内核主要的版本控制系统用以维护代码。因为BitKeeper为专有软件，这个决定在社区中长期遭受质疑。在Linux社区中，特别是 [Richard Stallman](https://en.wikipedia.org/wiki/Richard_Stallman) 与 [Free Software Foundation](https://en.wikipedia.org/wiki/Free_Software_Foundation) 的成员，主张应该使用开放源代码的软件来作为Linux核心的版本控制系统。Linus Torvalds 曾考虑过采用现成软件作为版本控制系统（例如 [Monotone](https://en.wikipedia.org/wiki/Monotone_software) ），但这些软件都存在一些问题，特别是性能不佳。现成的方案，如 [CVS](https://en.wikipedia.org/wiki/Concurrent_Versions_System) 的架构，受到 Linus Torvalds 的批评。

2005年，[Andrew Tridgell](https://en.wikipedia.org/wiki/Andrew_Tridgell) 写了一个简单程序，可以连接BitKeeper的存储库，BitKeeper著作权拥有者 [Larry McVoy](https://en.wikipedia.org/wiki/Larry_McVoy) 认为 Andrew Tridgell 对BitKeeper内部使用的协议进行逆向工程，决定收回无偿使用BitKeeper的授权。Linux内核开发团队与[BitMover](http://www.bitmovers.it/)公司进行蹉商，但无法解决他们之间的歧见。Linus Torvalds 决定自行开发版本控制系统替代BitKeeper，以十天的时间，编写出第一个git版本。


##安装git

git下载地址：https://git-scm.com/downloads

# 结语

这本书会持续更新，尽量让它与时俱进！

本文章从[此处]((https://darrenliuwei.com/git-github-tutorial/))搬运而来。

这本书是在GitHub上开源的，希望有兴趣的人能参与进来一起维护这本书！