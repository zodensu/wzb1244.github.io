# 献给写作者的 Markdown 新手指南

[TOC]

 在此，我们总结 Markdown 的优点如下：
 
 - 纯文本，所以兼容性极强，可以用所有文本编辑器打开。

 - 让你专注于文字而不是排版。

 - 格式转换方便，Markdown的文本你可以轻松转换为html、电子书等。

 - Markdown的标记语法有极好的可读性。

当然，我们既然如此推崇 Markdown ，也必定会教会你使用 Markdown ，这也是本文的目的所在。不过，虽然 Markdown 的语法已经足够简单，但是现有的 Markdown 语法说明更多的是写给 web 从业者看的，对于很多写作者来说，学习起来效率很低，现在，我们特地为写作者量身定做本指南，从写作者的实际需求出发，介绍写作者真正实用的常用格式，深入浅出、图文并茂地让您迅速掌握 Markdown 语法。

为了使您更好地学习，我们建议您登录[「简书」](http://www.ianshu.com)，将您的编辑器切换至 Markdown 编辑器，新建一篇空白笔记，然后点击右上角的预览模式。

或者下载一个[Atom](http://rj.baidu.com/soft/detail/39518.html?ald)，Atom里也有[Markdown插件](http://blog.csdn.net/qq_31915279/article/details/61824114)，安装好Markdown插件后可以不用理会那个插件，您就可以无视那个插件，直接用Markdown语言开始写作了。另外**Ctrl+Shift+M**是打开预览窗口的快捷键。

Atom这款软件很强大，可以说用它来写Markdown简直是**杀鸡焉用牛刀**。但因为我在用，在此就当顺便给您推荐了Atom这款软件吧。

转回正题。

# 标题
这是最为常用的格式，在平时常用的的文本编辑器中大多是这样实现的：输入文本、选中文本、设置标题格式。

而在 Markdown 中，你只需要在文本前面加上 # 即可，同理、你还可以增加二级标题、三级标题、四级标题、五级标题和六级标题，总共六级，只需要增加 # 即可，标题字号相应降低。例如：

```
# 一级标题
## 二级标题
### 三级标题
#### 四级标题
##### 五级标题
###### 六级标题
```
注：# 和「一级标题」之间建议保留一个字符的空格，这是最标准的 Markdown 写法。

你可以你的编辑器中尝试输入这六级标题，可以参考下方的截图：

![一级标题至六级标题](/img/format.jpg)
*一级标题至六级标题*

# 列表
列表格式也很常用，在Markdown中，你只需要在文字前面加上`-`就可以了，例如：

```
- 文本1
- 文本2
- 文本3
```
如果你希望有序列表，

也可以在文字前面加上 `1.` `2.` `3.` 就可以了，例如：
```
1. 文本1
2. 文本2
3. 文本3
```
*注：`-`、`1.`和文本之间要保留一个字符的空格。*

*列表案例截图如下：*
[](/img/format2.jpg)

在 Markdown 中，插入链接不需要其他按钮，你只需要使用 ``[显示文本](链接地址)`` 这样的语法即可，例如：

`[简书](http://www.jianshu.com)`

在 Markdown 中，插入图片不需要其他按钮，你只需要使用 ``![](图片链接地址) ``这样的语法即可，例如：

`![](http://upload-images.jianshu.io/upload_images/259-0ad0d0bfc1c608b6.jpg?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)`

*注：插入图片的语法和链接的语法很像，只是前面多了一个 `!`*

*插入链接和图片的案例截图：*
![](/img/format3.jpg)

# 引用

在我们写作的时候经常需要引用他人的文字，这个时候引用这个格式就很有必要了，在 Markdown 中，你只需要在你希望引用的文字前面加上 `>`这个英文的书名号就好了，例如：

`> 一盏灯， 一片昏黄； 一简书， 一杯淡茶。 守着那一份淡定， 品读属于自己的寂寞。 保持淡定， 才能欣赏到最美丽的风景！ 保持淡定， 人生从此不再寂寞。`

最终显示的就是：

> 一盏灯， 一片昏黄； 一简书， 一杯淡茶。 守着那一份淡定， 品读属于自己的寂寞。 保持淡定， 才能欣赏到最美丽的风景！ 保持淡定， 人生从此不再寂寞。

*引用的案例截图：*
![](/img/format4.jpg)

# 粗体和斜体

Markdown 的粗体和斜体也非常简单，用两个 `*` 包含一段文本就是粗体的语法，用一个 `*`包含一段文本就是斜体的语法。例如：

` *一盏灯*， 一片昏黄；**一简书**， 一杯淡茶。 守着那一份淡定， 品读属于自己的寂寞。 保持淡定， 才能欣赏到最美丽的风景！ 保持淡定， 人生从此不再寂寞。`

最终显示的就是下文，其中「一盏灯」是斜体，「一简书」是粗体：

 > *一盏灯*， 一片昏黄；**一简书**， 一杯淡茶。 守着那一份淡定， 品读属于自己的寂寞。 保持淡定， 才能欣赏到最美丽的风景！ 保持淡定， 人生从此不再寂寞。

 *粗体和斜体的案例截图：*

 ![](/img/format5.jpg)

 # 代码引用

 需要引用代码时，如果引用的语句只有一段，不分行，可以用 ```` 将语句包起来。
如果引用的语句为多行，可以将  ``` 置于这段代码的首行和末行。

*代码引用的案例截图：*

![](/img/format6.jpg)

# 表格

相关代码1：
```
| Tables        | Are           | Cool  |
| ------------- |:-------------:| -----:|
| col 3 is      | right-aligned | $1600 |
| col 2 is      | centered      |   $12 |
| zebra stripes | are neat      |    $1 |
```

显示效果：

<table border="1">
<tr>
  <td>Tables</td>
  <td>Are </td>
  <td>Cool </td>
</tr>
<tr>
  <td> col 3 is      </td>
  <td> right-aligned</td>
  <td>$1600 </td>
</tr>
<tr>
  <td> col 2 is   </td>
  <td> centered </td>
  <td> $12</td>
</tr>
<tr>
  <td> zebra stripes</td>
  <td> are neat  </td>
  <td>  $1 </td>
</tr>
</table>


相关代码2：

```
dog | bird | cat
----|------|----
foo | foo  | foo
bar | bar  | bar
baz | baz  | baz
```

显示效果：

<table border="1">
<tr>
  <td>foo</td>
  <td>foo</td>
  <td>foo</td>
</tr>
<tr>
  <td>bar</td>
  <td>bar</td>
  <td>bar</td>
</tr>
<tr>
  <td>baz</td>
  <td>baz</td>
  <td>baz</td>
</tr>
</table>

#  如果此格式不能正确显示表格，可换用html的格式：

代码如下：

```
<table border="1">
<tr>
  <td>foo</td>
  <td>foo</td>
  <td>foo</td>
</tr>
<tr>
  <td>bar</td>
  <td>bar</td>
  <td>bar</td>
</tr>
<tr>
  <td>baz</td>
  <td>baz</td>
  <td>baz</td>
</tr>
</table>
```

显示的内容会和上图一样：

<table border="1">
<tr>
  <td>foo</td>
  <td>foo</td>
  <td>foo</td>
</tr>
<tr>
  <td>bar</td>
  <td>bar</td>
  <td>bar</td>
</tr>
<tr>
  <td>baz</td>
  <td>baz</td>
  <td>baz</td>
</tr>
</table>

关于html表格的写法在[在此](http://www.w3school.com.cn/tags/tag_table.asp)

# 显示链接中带括号的图片
`![此处写注释，就是当你把鼠标放在图片上时自动显示的文字](此处放地址)`

- 代码如下：

`![title](/img/title.jpg)`

*这个title.jpg是我放在本地文件夹img文件夹的图片，如图：*
![在我的博客更新文件夹的最外层文件夹，所以我用的地址是“/img/”](/img/good.png)

或者

- 如下代码：

```
![][1]
[1]: http://latex.codecogs.com/gif.latex?\prod%20(n_{i})+1
```

# 结语

以上几种格式是比较常用的格式，所以我们针对这些语法做了比较详细的说明。除这些之外，Markdown 还有其他语法，如想了解和学习更多，可以参考这篇[『Markdown 语法说明』](http://wowubuntu.com/markdown/)。

强烈建议您现在就立马用 Markdown 写一篇文章吧，体会一下 Markdown 的优雅之处！

最后，希望我们的指南可以帮助到您，也希望[「简书」](https://www.jianshu.com/)能够成为您书写 Markdown 的最佳选择。

另外另外，又发现两个很好用的在线Markdown编辑网站：
[Cmd](https://maxiang.io/ )和[马克飞象](https://www.zybuluo.com/)
这两个在线编辑，如果你没有别的需求，只是纯粹想写Markdown的话，可以不用注册，直接用就好。

此文从此处搬运：

链接：https://www.jianshu.com/p/q81RER

來源：简书

著作权归作者所有。商业转载请联系作者获得授权，非商业转载请注明出处。