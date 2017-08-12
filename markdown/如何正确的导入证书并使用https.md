# 如何正确的导入证书并使用https
![](https://i1.piimg.com/1949/9dfb61dd226a52ce.jpg)

二话不说，进入正题！

## http和https是什么
<!--more-->
HTTPS（全称：Hyper Text Transfer Protocol over Secure Socket Layer），是以安全为目标的HTTP通道，简单讲是HTTP的安全版。即HTTP下加入SSL层，HTTPS的安全基础是SSL，因此加密的详细内容就需要SSL。 它是一个URI scheme（抽象标识符体系），句法类同http:体系。用于安全的HTTP数据传输。https:URL表明它使用了HTTP，但HTTPS存在不同于HTTP的默认端口及一个加密/身份验证层（在HTTP与TCP之间）。这个系统的最初研发由网景公司(Netscape)进行，并内置于其浏览器Netscape Navigator中，提供了身份验证与加密通讯方法。现在它被广泛用于万维网上安全敏感的通讯，例如交易支付方面。

网景在1994年创建了HTTPS，并应用在网景导航者浏览器中。 最初，HTTPS是与SSL一起使用的；在SSL逐渐演变到TLS时，最新的HTTPS也由在2000年五月公布的RFC 2818正式确定下来。
它是由Netscape开发并内置于其浏览器中，用于对数据进行加密和解密操作，并返回网络上传送回的结果。HTTPS实际上应用了Netscape的安全套接层（SSL）作为HTTP应用层的子层。（HTTPS使用端口443，而不是像HTTP那样使用端口80来和TCP/IP进行通信。）SSL使用40 位关键字作为RC4流加密算法，这对于商业信息的加密是合适的。HTTPS和SSL支持使用X.509数字认证，如果需要的话用户可以确认发送者是谁。
也就是说它的主要作用可以分为两种：一种是建立一个信息安全通道，来保证数据传输的安全；另一种就是确认网站的真实性，凡是使用了 https 的网站，都可以通过点击浏览器地址栏的锁头标志来查看网站认证之后的真实信息，也可以通过 CA 机构颁发的安全签章来查询 。

---以上是度娘的话---

## 配置证书
我用的是wdcp垃圾面板，况且wdcp网上很多错误教程，我就演示一下wdcp双引擎加证书吧！

打开Xshell5连接到服务器（其他ssh都行）

执行

```
nano /www/wdlinux/nginx/conf/vhost/此处一般为你的域名.conf
```

![](https://i2.buimg.com/1949/b7e3ee48ff371147.jpg)
```
        listen 443 ssl;
        ssl_certificate /www/ssl/你的域名_bundle.crt;
        ssl_certificate_key /www/ssl/你的域名.key;
        ssl_session_timeout 5m;
```
接着在指定位置放进证书即可！

## 遇到的问题
这可能也是最认真说（WATER!W-A-T-E-R!）的事情了。。。

### 出现不信任或不安全的证书
领完证书后会有三个文件，两个crt文件和一个key文件，key直接命名为    你的域名.key     上传到上述目录即可。


用记事本打开两个crt，将其中一个的内容复制到另一个（另一个证书初始内容不变），最后命名为    你的域名_bundle.crt    并上传到上述指定路径。

### typecho主题css无法加载
解决方法：在根目录的config-inc.php文件内新开一行，加入以下代码
```
/** 载入https支持 */
define('__TYPECHO_SECURE__',true);
```

### 图片导致小红锁消失
推荐使用yotuku.cn提供的图床服务，链接前改为https即可！

### 多说导致小红锁消失
首先，咱们需要多说的embed.js这个文件，地址在http://static.duoshuo.com/embed.js，下载到本地后上传服务器，在typecho主题配置中填写你embed.js的https的地址。没有配置的在header.php或footer.php或comments.php或comment.php寻找embed.js，改为你embed.js的https地址！

### 多说头像导致小红锁消失
网上有很多nginx配置文件反代（反向代理）多说头像的，非常麻烦，其实我们只要一个php文件就能搞定！


根目录新建一个名叫avatar.php的文件，内容为

```
<?php
ob_start();
$src = $_GET['s'];
$src = preg_replace('/http:\/\/.+\.gravatar\.com/', 'http://cn.gravatar.com', $src);
$timeout = stream_context_create(array(
 'http' => array(
  'timeout' => 1.0
 )
));
$data = file_get_contents($src, 0, $timeout);
if ($src != 'null') {
 header('Content-Type:image/png');
 if (substr($data, 0, 3) === "\xFF\xD8\xFF" || substr($data, 1, 3) === "\x50\x4E\x47") {
  echo $data;
 } else {
  echo file_get_contents(dirname(__FILE__) . "/none.jpg", 0, $timeout);
 }
} else {
 echo file_get_contents(dirname(__FILE__) . "/none.jpg", 0, $timeout);
}
```

<del>然后在根目录放[这张图片](https://zhenbang.pw/none.jpg)，这句话有超链接喔！</del>自己找一下，百度图片搜索默认头像，然后命名为none.jpg放在根目录。

打开embed.js，搜索

```
avatarUrl: function(e) {
                return e.avatar_url || rt.data.default_avatar_url
            }
```

替换为

```
avatarUrl: function(e) {
                return 'https://你的域名/avatar.php?s='+e.avatar_url || 'https://你的域名/avatar.php?s='+nt.data.default_avatar_url
            }
```

很简单吧！（至少比那些忙着搭建镜像还必须要nginx的好多了！）

### 泡泡表情七牛导致小黄锁消失
改成阿里云oss或者腾讯云cos就可以啦！（这一段特别WATER!W-A-T-E-R!）

### 网易云音乐导致小黄锁消失
yodubgm最新版已经修复该问题
## 总结
<del>对于https，个人博客是完全没必要的，不过为了那可爱的小红锁n(*≧▽≦*)n，哈哈！</del>
现在，google对https的网站收录好得多，并且没有https的网站chrome浏览时会出现“不安全”字样，所以https还是<em><strong>有必要的</strong></em>，不过我没有条件，买的虚拟主机不支持https。