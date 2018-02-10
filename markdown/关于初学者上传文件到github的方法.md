# 关于初学者上传文件到github的方法

[TOC]

说来也惭愧，我是最近开始用github，小白一个，昨天研究了一个下午。终于可以上传了，所以今天写点，一来分享是自己的一些经验，二来也是做个记录，万一哪天又不记得了:)
废话不多说，直接来，这次主要介绍的是windows下的安装和使用。

## 【第一步】建立先仓库
第一步的话看一般的提示就知道了，在[github](https://github.com)新建一个repository（谷歌可以解决），都是可视化的界面操作，所以难度不大。或者看这里：[新建一个资料库](https://help.github.com/articles/create-a-repo) 这是官方help，虽然是英文的，但是基本都是图和代码，所以很容易读懂。

　　1.在github首页的右上角，点击红框中的Create New Repo。
　　2.进入新建仓库的界面
　　3.填一下仓库名称，Initialize this repository with a README是可选的，不过本人建议最好选上，可以在后面省一个步骤。填好之后，点Create repository就行了。
## 【第二步】克隆仓库
第二步开始就基本进入命令行模式了，不过要先从github上下载命令行工具。[下载地址](http://windows.github.com/) 在此。

　　然后进行简单的安装之后，会在桌面上创建两个图标，GitHub和Git Shell，GitHub是图形界面，Git Shell是命令行模式，而且默认的Git仓库是建在C盘的，个人建议要把路径重设下。

　　点开Git Shell，进入命令行。首先我们先要把GitHub上的我们新建的仓库clone下来，为了演示，我在GitHub上新建了一个名称为myRepoForBlog的git。

　　在初始化版本库之前，先要确认认证的公钥是否正确，如下：
                      
    ssh -T git@github.com
正确的结果应如下：

    　Warning: Permanently added 'github.com,207.97.227.239' (RSA) to the list of known hosts.

      Hi findingsea! You've successfully authenticated, but GitHub does not provide shell access.

　　会有一个Warning，不用理会。

　　接下对库进行clone，如下：
     
     git clone https://github.com/findingsea/myRepoForBlog.git

上面的地址可以在如下界面找到：
![注意图片所示的内容最好完全一致](/img/trimeteach.jpg)

把这个刚刚copy成功的地址**右键**粘贴在`git clone `后面，

clone成功如下：

     　Cloning into 'myRepoForBlog'...
    Warning: Permanently added 'github.com,207.97.227.239' (RSA) to the list of known hosts.
    remote: Counting objects: 3, done.
    remote: Total 3 (delta 0), reused 0 (delta 0)
    Receiving objects: 100% (3/3), done.

总之就是看到很多done，就是 成功了。
克隆成功后你会看到一个文件夹，在你刚刚`git bash here`的那个界面。

## 【第三步】上传README.md文件

这个时候，我们的GitHub文件夹下就多了一个myRepoForBlog文件夹，进入文件夹目录，对仓库进行初始化，如果我们之前没有勾选创建README，则要先创建README.md文件![Alt text](https://pic002.cnblogs.com/images/2012/162517/2012082717042735.png)
，不然上传文件会报错。如果在第一步就勾选过了，则可以直接进入下列的 *第四步* 。

    　　1.git init
    　　2.touch README.md
    　　3.git add README.md
    　　4.git commit -m 'first_commit'
    　　5.git remote add origin https://github.com/findingsea/myRepoForBlog.git
    　　6.git push origin master

## 【第四步】push文件
创建完README.md后，就可以push了，代码类似。

    1.git add .
    2.git commit -m 'first_commit'
    3.git remote add origin https://github.com/findingsea/myRepoForBlog.git
    4.git push origin master

如果执行
`git remote add origin https://github.com/findingsea/myRepoForBlog.git`
出现错误：
`fatal: remote origin already exists`

则执行以下语句：

      git remote rm origin
再往后执行
`git remote add origin https://github.com/findingsea/myRepoForBlog.git `即可。

在执行git push origin master时，报错：
`error:failed to push som refs to.......`

则执行以下语句：
`git pull origin master`

先把远程服务器github上面的文件拉先来，再push 上去

## 【结束】
再次要强调这篇文章主要是对初学者的，也就我这种github菜鸟的。

最后感谢那些无私分享自己经验和知识的博主们.

最最后，初学者如果没有人手把手教过你，也就是没有最直接的经验者给你经验之前，建议多方查阅资料后经过思考之后再选择一个教程。因为系统因每个人的习惯而有所差别，有可能在别人的电脑上能顺利地一次成功，但在你的电脑上未必，这些小细节有因为为能及时意识到而耽误你的时间。

以下是本文的参考资料：

[git/github学习笔记](http://www.cnblogs.com/fnng/archive/2011/08/25/2153807.html)
[git/github使用方法小记](http://artori.us/git-github-usage/)
[在github上分享和展示你的小代码](https://serholiu.com/github-share-code)