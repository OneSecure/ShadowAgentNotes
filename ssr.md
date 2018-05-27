# 纯手工搭建 ShadowsocksR 服务器教程 (搬瓦工主机)

<img src="ssr/title.png" />

## 前言
由于 搬瓦工 目前已经将 一键安装 SS/SSR 功能取消了. 特编写此详细手工安装 SSR 服务器 教程. 

我希望一无所知的小白也能按此教程完成安装. 看到这篇文章的人, 请以任何方式转发到网络上的任何地方. 作者放弃版权.

至于 搬瓦工 VPS 的购买小白教程, 请戳 [这里](https://github.com/OneSecure/ShadowAgentNotes/blob/master/KillGFW.md)

最后再提醒一句. 由于搬瓦工网站已经被墙, 本文的所有操作必须在你已经使用别的方式翻着墙的状态下进行.

## 步骤

1. 首先停止 VPS 主机. 在 "Main controls" 页面, 点击 "stop" 按钮, 就停止了主机. 

    <img src="ssr/start.png" />

2. 在 "Root password modification" 页面, 点击 "Generate and set new root password" 按钮. 
    系统就为你生成新的 `root` 密码.
   
    <img src="ssr/root-password.png" />
   
