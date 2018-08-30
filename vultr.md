# 在 Vultr 主机上搭建 SSR 服务器 图文教程

<a href="https://www.vultr.com/?ref=7492090"><img src="https://www.vultr.com/media/banner_1.png" width="728" height="90"></a>

## 步骤

1. 注册帐户并登录 [Vultr](https://www.vultr.com/?ref=7492090)

2. 如果你新注册的账号, vultr 会有 10 美元的赠金. 当然你得首先 `绑定信用卡` 或者 `充值5美元` 才能到账. 下图是通过 `paypal` 充值的图文过程.

   注意, 赠金必须在90天内花完, 否则过期作废.

<img src="vultr/billing.png" />

<img src="vultr/paypal.png" />

3. 然后回到 `Servers` 标签页, 点击右侧的加号 `+` 创建虚拟主机.

<img src="vultr/server.png" />

4. 选择主机机房的位置, 有 `日本`, `新加坡`, `荷兰`, `法国`, `德国`, `英国`, `澳洲`, `美国` 等供选择, 
   我选了个 `亚特兰大`, 白天还行, 晚上卡出翔; 据说 `日本` 的也很卡, 慎选; 另据说 `硅谷` 的不错, 希望是真的.

<img src="vultr/location.png" />

5. 选择 `操作系统` 类型, 建议选择 `CentOS 7 x64`

<img src="vultr/type.png" />

6. 主机容量, 选 3.50 美元每月 档次的, 支持 IPv4, 500GB 每月 流量, 可劲 `造` 也用不完.

<img src="vultr/size.png" />

7. 剩下的就没什么了, 第七栏, 填写主机名, 我填的是 `v-01`, 你们随意. 
   最后点击 `部署` (Deploy Now), 完成 虚拟主机 的创建.

<img src="vultr/deploy.png" />

