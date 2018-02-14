# 理解GitHub流（UnderStanding the GitHub Flow）

GitHub Flow is a lightweight, branch-based workflow that supports teams and projects where deployments are made regularly. This guide explains how and why GitHub Flow works.
GitHub 流是一个轻量级、基于分支的工作流，用于支持团队和项目的定期部署。这个指南解释了GitHub流如何运作以及为什么这么运作。



## 1.Create a branch创建分支
![第一张](/img/Createabranch.jpg)
When you're working on a project, you're going to have a bunch of different features or ideas in progress at any given time – some of which are ready to go, and others which are not. Branching exists to help you manage this workflow.

When you create a branch in your project, you're creating an environment where you can try out new ideas. Changes you make on a branch don't affect the `master` branch, so you're free to experiment and commit changes, safe in the knowledge that your branch won't be merged until it's ready to be reviewed by someone you're collaborating with.

当你进行一个项目的工作时，随着项目的推进在某一时间段，你会有一些的不同的意见（features）或想法，其中一些会有用，一些会没用。分支帮你管理这些工作流。 
当你创建了一个项目分支，相当于创建了一个可以尝试任何新想法的区域。在这个分支上的更改不会影响master主分支，这样你就可以随意进行试验并且提交修改，并且不用担心你的分支会合并，直到它已经准备好了去被你的合作者去检查（review）。

### ProTip窍门：

Branching is a core concept in Git, and the entire GitHub Flow is based upon it. There's only one rule: anything in the `master` branch is always deployable.

Because of this, it's extremely important that your new branch is created off of master when working on a feature or a fix. Your branch name should be descriptive (e.g., `refactor-authentication`, `user-content-cache-key`, `make-retina-avatars`), so that others can see what is being worked on.

分支是Git的核心概念，整个GitHub流都建立在它的基础上。唯一的规则是：master主分支中的任何东西都是可以进行扩展的。 
基于这项规则，在你进行新的开发以及修改项目时，参照master主分支建立新的分支是非常重要的。你在分支取名时应该进行项目描述（比如：重构-项目名，增加功能–项目名–某功能），这样其他人就能知道这个分支是用来做什么的。


## 2.Add commits添加提交
![第二张](/img/Addcommits.jpg)
Once your branch has been created, it's time to start making changes. Whenever you add, edit, or delete a file, you're making a commit, and adding them to your branch. This process of adding commits keeps track of your progress as you work on a feature branch.

Commits also create a transparent history of your work that others can follow to understand what you've done and why. Each commit has an associated commit message, which is a description explaining why a particular change was made. Furthermore, each commit is considered a separate unit of change. This lets you roll back changes if a bug is found, or if you decide to head in a different direction.

一旦你的分支被创建，你就可以开始进行修改了。每当你进行增加、修改、删除文件，你都在做一个提交，并且将他们添加到你的分支上。这种添加提交的处理方式把你对项目的工作都记录在一个特定的分支上。 
提交会创建一个透明的工作记录，这样你的同伴可以以此去理解你做了什么以及为什么这样做。不同的提交会有一个相关的提交信息，用来描述和解释你做的特殊修改。此外，每个提交都是一个独立的单元。这样你可以在发现bug或者决定换一个方向时进行回退。

### ProTip

Commit messages are important, especially since Git tracks your changes and then displays them as commits once they're pushed to the server. By writing clear commit messages, you can make it easier for other people to follow along and provide feedback.

提交信息（Commit messages）很重要，特别是Git 在记录了你的修改并且显示将会发布到服务中。通过清晰的提交信息（Commit messages），可以让其他人在遵循你的规则及提供反馈时变得容易些。

## 3.Open a Pull Request开启一个提交请求
![第三张](/img/openapullrequest.jpg)
Pull Requests initiate discussion about your commits. Because they're tightly integrated with the underlying Git repository, anyone can see exactly what changes would be merged if they accept your request.

You can open a Pull Request at any point during the development process: when you have little or no code but want to share some screenshots or general ideas, when you're stuck and need help or advice, or when you're ready for someone to review your work. By using GitHub's @mention system in your Pull Request message, you can ask for feedback from specific people or teams, whether they're down the hall or ten time zones away.

提交请求（Pull Request）会发起一个关于你的提交的讨论。因为他们紧密关联着最底层的Git 仓库，任何人都能清楚的看到如果他们同意你的请求将会有什么样的变化被合并。 
你可以在项目的任何开发点上开启一个提交请求（Pull Request）：当你编辑了少量代码或者根本没有代码但想分享一些屏幕截图或一些想法时，当你项目卡住需要帮助和建议时，或者当你准备好让某些人检查你的工作时。在提交请求中通过使用GitHub的“@提醒（@mention）” 系统，你可以向指定的人或团队询问反馈，无论他们身处何时何地。

### ProTip

Pull Requests are useful for contributing to open source projects and for managing changes to shared repositories. If you're using a Fork & Pull Model, Pull Requests provide a way to notify project maintainers about the changes you'd like them to consider. If you're using a Shared Repository Model, Pull Requests help start code review and conversation about proposed changes before they're merged into the master branch.

提交请求（Pull Requests）对于建设开源的项目和管理分享仓库中的修改非常有用。如果你使用 Fork&Pull 模式，提交请求（Pull Requests）提供了一个方式去提醒项目维护者有关你希望他们去考虑的修改。如果你使用分享仓库模式（Shared Repository Model），在管理者合并你的修改至（master）主分支之前，提交请求（Pull Requests）会开启一个关于已提交代码的检查及讨论。


## 4.Discuss and review your code讨论和检查（review）你的代码
![第四张](/img/Dsicussandreviewyourcode.jpg)
Once a Pull Request has been opened, the person or team reviewing your changes may have questions or comments. Perhaps the coding style doesn't match project guidelines, the change is missing unit tests, or maybe everything looks great and props are in order. Pull Requests are designed to encourage and capture this type of conversation.

You can also continue to push to your branch in light of discussion and feedback about your commits. If someone comments that you forgot to do something or if there is a bug in the code, you can fix it in your branch and push up the change. GitHub will show your new commits and any additional feedback you may receive in the unified Pull Request view.

一次提交请求（Pull Request）开启后，其他人或团队通过检查你的修改或许会有问题或者评论。或许编码风格不符合程序的编码方针，修改没有写单元测试，或者一些看起来都非常好并且符合规则。提交请求（Pull Request）的设计鼓励这种类型的交流。 
你也可以继续提交你的分支到关于你提交内容的讨论和反馈中去。如果有人评论了你忘了做某些事或者发现你代码中的一个bug，你可以在你的分支中修复它并且增加到修改上。GitHub 将会在一个统一的提交请求（Pull Request）展示中展示新的提交和任何附加的回馈。

### ProTip

Pull Request comments are written in Markdown, so you can embed images and emoji, use pre-formatted text blocks, and other lightweight formatting.

提交请求（Pull Request）评论通过MarkDown语言拼写，所以你可以嵌入图片和表情，使用预编译的文本块，或者进行轻量的格式化

## 5.Deploy部署
![第五张](/img/Doplay.jpg)
With GitHub, you can deploy from a branch for final testing in production before merging to master.

Once your pull request has been reviewed and the branch passes your tests, you can deploy your changes to verify them in production. If your branch causes issues, you can roll it back by deploying the existing master into production.

一旦你的提交请求（Pull Request）经过审查并且分支通过了测试，你可以部署你的修改到在生产模式中去验证它。如果你的分支引起问题，你可以通过回滚去部署当前的master主分支到生产模式中。

## 6.Merge合并
![第六张](/img/Merge.jpg)
Now that your changes have been verified in production, it is time to merge your code into the master branch.

Once merged, Pull Requests preserve a record of the historical changes to your code. Because they're searchable, they let anyone go back in time to understand why and how a decision was made.

现在你的修改已经在生产模式中得到了验证，是时候合并你的代码到master主分支中了。 
一旦合并，提交请求（Pull Request）会在你的代码中保存一个历史变更记录。因为它是可被搜索的，它可以让任何人在回头看时理解为什么和如何做出的这个决定。

### ProTip

By incorporating certain keywords into the text of your Pull Request, you can associate issues with code. When your Pull Request is merged, the related issues are also closed. For example, entering the phrase` Closes #32` would close issue number 32 in the repository. For more information, check out our [help article](https://help.github.com/articles/closing-issues-via-commit-messages).
通过合并某一关键词到你的提交请求中（Pull Request），你可以通过代码进行关联评论。当你的提交请求（Pull Request）被合并，相关讨论将被关闭。比如，当前有三十二条评论，那么将在仓库中记录这三十二条评论。更多信息，可通过帮助文章（help article）获取。
