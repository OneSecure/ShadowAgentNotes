# 在 Vultr 主机上搭建 SSR 服务器 图文教程

<a href="https://www.vultr.com/?ref=7492090"><img src="https://www.vultr.com/media/banner_1.png" width="728" height="90"></a>

- 说明: V家 的 VPS 其实速度不是很快, 夜里上网高峰时段更是龟速. 但好处是显而易见的: **可以随意换 IP**, 这点对 `墙国` 的网民至关重要. 当 虚拟主机 IP 被墙, 可以删掉此主机, 再创建一新的, IP 就变了, 举手之劳.

## 索引
- [创建虚拟主机](#创建虚拟主机)
- [部署 ShadowsocksR (SSR) 服务器](#部署-shadowsocksr-ssr-服务器)

## 创建虚拟主机

1. 在 [Vultr](https://www.vultr.com/?ref=7492090) 上注册帐户并登录.

2. 如果你新注册的账号, vultr 会有 10 美元的赠金. 当然你得首先 `绑定信用卡` 或者 `充值5美元` 才能到账. 
   作者不愿随意泄漏自己的信用卡信息给商家, 因此使用`贝宝`充值.
   下图是通过 `paypal` 充值的图文过程.

   注意, 赠金必须在90天内花完, 否则过期作废.

<img src="vultr/billing.png" />

<img src="vultr/paypal.png" />

3. 然后回到 `Servers` 标签页, 点击右侧的加号 `+` 创建虚拟主机.

<img src="vultr/server.png" />

4. 选择主机机房的位置, 有 `日本`, `新加坡`, `荷兰`, `法国`, `德国`, `英国`, `澳洲`, `美国` 等供选择, 
   作者随意选了个 `亚特兰大`, 发现白天还行, 晚上就卡出翔; 据说 `日本` 的也很卡, 慎选; 另据说 `硅谷` 的不错, 希望是真的.

<img src="vultr/location.png" />

5. 选择 `操作系统` 类型, 建议选择 `CentOS 7 x64`

<img src="vultr/type.png" />

6. 主机容量, 选 3.50 美元每月 档次的, 支持 IPv4, 500GB 每月 流量, 可劲 `造` 也用不完.

<img src="vultr/size.png" />

7. 剩下的就没什么了, 第七栏, 填写主机名, 作者填的是 `v-01`, 你们随意. 
   最后点击 `部署` (Deploy Now), 完成 虚拟主机 的创建. 过程持续 5 分钟左右.

<img src="vultr/deploy.png" />

8. 创建好的主机像下图的样子, 点击 `Manage` 按钮进入主机信息页面.

<img src="vultr/created.png" />

9. 在 `主机信息` 页面, 可以看到 `IP Address`(IP地址), 用户名 root, 登录密码 等关键信息. 
   这里把 `SSH` 端口号 `22` 漏掉了, 我用红字添了上去. 

   由于很多 IP 已经被 GFW 屏蔽, 安装完成, 并从控制台确认系统已经在运行以后, 请在 [这个网站](http://tool.chinaz.com/port/) 上用主机 IP 和 22 端口试一下, 看是否畅通, 如果不通, 请再次新建 `虚拟主机`, 直到试通为止. 然后再把不用的虚拟主机删除. 

   最后, 如图所示, 以 `root` 用户名 和 `密码` 登入主机. 

<img src="vultr/host.png" />

## 部署 ShadowsocksR (SSR) 服务器

在主机内的命令行窗口敲入以下命令.
每次输入一行、回车，等待屏幕上的操作完成后再输入下一条。

```bash
sudo su
wget --no-check-certificate https://raw.githubusercontent.com/teddysun/shadowsocks_install/master/shadowsocksR.sh
chmod +x shadowsocksR.sh
./shadowsocksR.sh 2>&1 | tee shadowsocksR.log
```

最后一步输入完毕并回车后，你应该会看到有几个地方询问你, 要求你填写密码, 输入端口号, 选定协议, 等等, 按照提示输入你自己的选项并回车即可。
如果你懒, 一路回车也可以, 脚本会用预设值为你生成配置. 
然后你什么都不用做，只需要静静地等它运行完毕就好。结束后你就会看到部署好的 ShadowsocksR 的配置信息。
下图是作者的安装结果.

<img src="vultr/ssr.png" />

记下红色高亮的内容，就是服务器 IP、服务器端口、你设的密码和加密方式, 混淆, 协议 等等配置信息, 
把它们输入你手机, 电脑上的 SSR 客户端就可以 翻墙啦。
