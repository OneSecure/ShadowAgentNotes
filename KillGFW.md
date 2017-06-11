# 搬瓦工搭建 Shadowsocks 服务器(一键搭建)详细图文教程

(小白不要惶恐, 只要你看得懂中文, 有初中英文水平, 有支付宝账号, 你就可以在十分钟之内购买一个美国虚拟主机并且在它上面搭好 Shadowsocks 服务器.) 

> 前言

相信来看这文章的同学都知道什么是`翻墙`了吧，我就不重复说了。
只要是详细的介绍用 [搬瓦工](https://bandwagonhost.com/aff.php?aff=12816) 搭建 Shadowsocks 服务器来翻墙。

> `搬瓦工来自 = bandwagonhost，一家美国的 VPS 服务商`

Shadowsocks 是目前最好的翻墙的工具，没有之一。
为什么用搬瓦工搭建 Shadowsocks 服务器？因为性价比高，呵呵。
最便宜的只要 20 美金一年，每月 500G 流量。(套餐在下面会详细介绍的)

## 需要准备的东西

*   能上网的电脑（废话了）
*   一张银行卡，并且已经开通网银，信用卡也行，~~PayPal 付款的时候需要（说着当然肯定要有钱的呀），~~ 或者支付宝（最近才支持）。
*   睁大眼睛看教程，一次不会的话，看多一次，还是不会的话，那再看一次~

> ### 教程开始~

### 温馨提示（2016-7-30更新）

*   由于下面的教程搭建翻墙环境的服务器是在美国的，速度可能不是很快。
*   由于官网属于被墙的状态，如你在下面点击链接打开官网显示出错，建议你首先用别的方式翻着墙,这是个鸡生蛋蛋生鸡的悖论,我目前无法解决.

## 现已支持支付宝交易

*   应该是最近些天开始支持的，说白了就是搬瓦工官方人员知道我们大天朝内太多人们需要从那里购买 VPS 搭建 Shadowsocks 来翻墙。
*   没办法，面对这个奇葩的大天朝，外国佬还是挺会做事的，从之前配置了一键安装 Shadowsocks Server 再到现在支持支付宝交易，我大天朝内人们折腾自己搭建翻墙环境又将更加简单，小白化，也感谢他们官网的机智，了解国情。
*   下面的注册 Paypal 账号教程请跳过吧。

## ~~先注册 Paypal 国际账号~~

*   ~~这是购买搬瓦工付款必备的。~~
*   ~~`如果你有 Paypal 账号，请确定是国际账号的，国内的 Paypal 是付款不了的`~~
*   ~~`已有 Paypal 国际账号的请跳过这步`~~
*   ~~如果你银行卡没有开通网银或者是不想注册 Paypal，可以找我代购。~~
*   ~~Paypal 国际账号注册地址：[https://www.pay<wbr>pal.com/c2/home](https://www.paypal.com/c2/home)~~
*   ~~打开之后，选择右上角的`“注册”`~~
*   ~~然后选择`“个人”`——`“立即开始”`~~
*   ~~再然后按照提示填写自己的信息，需要注意的是：`注册 PayPal 账户的姓名必须与您的银行账户开户名完全一致`,还有就是如果密码太简单了，是无法创建账号的。~~
*   ~~同意并创建账号—-输入验证码—-`继续`~~
*   ~~设置密码提示问题——`提交`~~
*   ~~之后你就会看到`“祝贺您！您已注册PayPal账户”`,再然后呢，输入你的银行卡号，再选择：`是`，然后：`提交`~~
*   ~~至此你已经完成 Paypal 账号的注册。（^_^好简单是不是）~~

## 看看搬瓦工套餐吧

| 名称 | 10G KVM – PROMO | 20G KVM – PROMO |
| --- | --- | --- |
| CPU | 1x Intel Xeon | 2x Intel Xeon |
| 内存 | 512 MB | 1024 MB |
| 硬盘 | 10 GB/SDD RAID-10 | 20 GB/SDD RAID-10 |
| 流量 | 500 GB/月 | 1 TB/月 |
| 带宽 | 1 Gigabit | 1 Gigabit |
| 价格 | 19.99美元/年 | 49.99美元/年 |
| 链接 | [购买](https://bandwagonhost.com/aff.php?aff=12816&pid=43) | [购买](https://bandwagonhost.com/aff.php?aff=12816&pid=44) |

`以上参数均来自官网`

*   上面列出的套餐只是一部分，也是自我搭建 Shadowsocks 服务器推荐的套餐。
*   说着当然，你土豪的话也可以选择其他的套餐，或者购买 `linode` 的 VPS。
*   有多个套餐，我应该选择哪个啊？
*   如果只是自己一个人用，想体验一下，强烈推荐选择套餐1就好，毕竟够用就好，不要浪费。感觉不错的话，是可以升级到其他的套餐的
*   一般来说，如果只是个人普通使用，哪个便宜选择那个，说着当然如果你使用量比较多或者想要分享给同学和朋友一起用的话，选择合适的套餐即可。又或者你土豪的话，选择最贵的也行。
    注意，记住一分钱一分货。

## 好啦，开始购买搬瓦工

*   火速打开 [官网](https://bandwagonhost.com/aff.php?aff=12816)
*   如果你只想购买套餐1，就点击这个 [链接](https://bandwagonhost.com/aff.php?aff=12816&pid=43) ,然后选择后面的：`order Now`

    ![tu](https://raw.githubusercontent.com/OneSecure/ShadowAgentNotes/master/image/001.jpg)

*   需要说明的是：在 `Billing Cycle` 选项那里选择：`$xxx USD Annually`，每年付 XXX 元的意思。
*   其次需要注意的是：在 `location` 选项那里选择 `US West Coast - Los Angeles (USCA_2)` 或者 `US West Coast - Arizona (USAZ_2)`，注意！这是选择服务器的地区，是直接影响到你的访问速度的。
*   然后点击`Add To Cart`

    ![tu](https://wx1.sinaimg.cn/large/a8c38b53gy1fg63k5mt8xj20op0a3whw.jpg)

*   再然后点击 `Checkout`
*   提示你要注册账号，请按照下面图片提示来填写~

    ![tu](https://raw.githubusercontent.com/OneSecure/ShadowAgentNotes/master/image/003.jpg)

*   下面图片是参考，要注意的是，`Country` 选项记得选择 `China`。不要忘了勾上 `I have read and agree to the Terms of Service`， 然后 `Complete Order`
*   重要提示！现在已支持 `支付宝` 交易。
*   `Payment Method` 的时候选择 `Credit Card and AliPay (Stripe)` 就好！
*   支持方式选择 `Credit Card and AliPay (Stripe)` 之后，然后 `Complete Order`，再然后 `Pay now`，你就会有看到有 `支付宝` 的登录窗口，支付又变得简单了。科科。

    ![tu](https://wx3.sinaimg.cn/large/a8c38b53gy1fg63kb63k3j20hv0gn0ym.jpg)

*   ~~如果你选择的是 paypal，并 `Complete Order` 的话~~
*   ~~然后就会自动跳转到 Paypal 付款界面。~~
*   ~~登录之前注册的 Paypal 账号，然后选择 `立即付款`~~
*   ~~下面这已是付款成功的^_^(这图片来自我帮我同学购买搬瓦工付款成功的截图)~~

    ![tu](https://wx1.sinaimg.cn/large/a8c38b53gy1fg62lr5ozzj20mm0b1q53.jpg)

## 安装 Shadowsocks 服务器

*   确保你已经成功付款之后, 打开： [https://bandwagonhost.com/clientarea.php?action=products](https://bandwagonhost.com/clientarea.php?action=products)

    ![tu](https://wx3.sinaimg.cn/large/a8c38b53gy1fg62ltnycyj20ml02qdge.jpg)

*   选择 `KiwiVM Control Panel`
*   这是首次登录的界面，稍等一会，等待资源分配即可。

    ![tu](https://wx4.sinaimg.cn/large/a8c38b53gy1fg62lw7hj0j20hu04l3zi.jpg)

*   这是登录后的界面，里面有详细的关于服务器运行的情况，比如说，流量的使用。这些先不管它，安装
    Shadowsocks 服务器先，搬瓦工已经为我们准备 Shadowsocks 服务器的安装，呵呵，不用打命令了，一键安装。在左边选择 `Shadowsocks Server`

    ![tu](https://wx3.sinaimg.cn/large/a8c38b53gy1fg62lyicvvj20n70ebtd2.jpg)

*   然后选择 `Install Shadowsocks Server`
*   等待安装完成之后选择 `Go Back`
*   Shadowsocks Server 在运行~

    ![tu](https://wx1.sinaimg.cn/large/a8c38b53gy1fg62m1j4jkj20h007pta0.jpg)?

*   至此, Shadowsocks 服务器安装完毕.

## What’s next?（来自搬瓦工说明）

1.  步骤1, 安装Shadowsocks GUI应用程序
2.  Windows 7或更早, 下载[shadowsocks-win-2.3.zip](https://kiwivm.it7.net/dist/shadowsocks-win-2.3.zip)(已安装客户端请忽略)
3.  Windows 8或更高版本,下载[shadowsocks-win-dotne<wbr>t4.0-2.3.zip](https://kiwivm.it7.net/dist/shadowsocks-win-dotnet4.0-2.3.zip)(已安装客户端请忽略)
4.  或者,您可以在开发者的网站下载最新版本:[http://sourceforge.net/projects/shadowsocksgui/files/dist/](http://sourceforge.net/projects/shadowsocksgui/files/dist/)
5.  下载后,提取zip文件并启动Shadowsocks.exe
6.  如果您没有看到如下所示的设置窗口,然后找到Shadowsoc<wbr>ks托盘图标并双击：
7.  步骤2，Shadowsocks GUI设置
8.  进入设置如下所示
9.  请注意,您可以简单地复制粘贴标记为黄色的字段:

    ![tu](https://wx1.sinaimg.cn/large/a8c38b53gy1fg62m41jvjj20de08pmyf.jpg)

然后点击确定

10.  不要忘记了勾上`启用系统代理`（鼠标右键 Shadowsocks 托盘图标）

    ![tu](https://wx3.sinaimg.cn/large/a8c38b53gy1fg62m5z988j209v06maao.jpg)

至此，Shadowsocks 服务器已经安装完成，尽情的翻墙吧!

## 下面是一些使用说明

*   我怎么修改 Shadowsocks 服务器的密码？
    答：在Shadowsocks server controls下点击Generate new password
*   我怎么修改Shadowsocks服务器的端口？
    答：在Shadowsocks server controls下点击Change port
*   我怎么修改Shadowsocks服务器的加密方式？
    答：在Shadowsocks server controls下点击Change encryption，然后选择要更改的加密方式之后save，然后Go back
*   我的KiwiVM Control Panel账号是什么呀？
    答：你的服务器IP地址
*   我怎么修改KiwiVM Control Panel密码？
    答：在登录KiwiVM Control Panel界面的时候选择左边KiwiVM password modification，输入新密码后，点击Set new password

## 手机端的使用方法（Android）

*   下载地址：[http://pan.baidu.com/s/1bni3kYz](http://pan.baidu.com/s/1bni3kYz)
*   下载完成后，安装，打开。
*   服务器：填写你的服务器IP
*   远程端口：填写你的服务器的远程端口，比如默认是443
*   本地端口：1080
*   密码：填写你的 Shadowsocks 服务器的密码
*   加密方式：选择相对应的加密方式，例如AES-256-CFB或<wbr>者RC4-MD5.
*   路由：选择绕过局域网及中国大陆地址
*   勾上全局代理
*   然后右上角！启用

## 手机端的使用方法（iOS）

*   请在苹果 App Store 内下载 [网际飞梭](https://itunes.apple.com/cn/app/id982708939?mt=8) 软件.  
*   下载完成后，安装，打开, 配置方法与 Android 类似。

    ![tu](https://wx4.sinaimg.cn/large/a8c38b53gy1fg62oi314kj20c00bvt9u.jpg)
