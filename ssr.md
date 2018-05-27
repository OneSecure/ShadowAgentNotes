# 纯手工搭建 ShadowsocksR 服务器教程 (搬瓦工主机)

<img src="ssr/title.png" />

## 前言
由于 搬瓦工 目前已经将 一键安装 SS/SSR 功能取消了. 特编写此详细手工安装 SSR 服务器 教程. 

我希望一无所知的小白也能按此教程完成安装. 看到这篇文章的人, 请以任何方式转发到网络上的任何地方. 作者放弃版权.

至于 搬瓦工 VPS 的购买小白教程, 请戳 [这里](https://github.com/OneSecure/ShadowAgentNotes/blob/master/KillGFW.md)

最后再提醒一句. 由于搬瓦工网站已经被墙, 本文的所有操作必须在你已经使用别的方式翻着墙的状态下进行.

## 步骤

1. 首先停止 VPS 主机. 在 `Main controls` 页面, 点击 `stop` 按钮, 就停止了主机. 

    <img src="ssr/start.png" />



2. 在 `Root password modification` 页面, 点击 `Generate and set new root password` 按钮. 
    系统就为你生成新的 `root` 密码.
   
    <img src="ssr/root-password.png" />
   
    请注意, 系统`不会`为你`保存`这里生成的`密码`, 请马上将其复制粘贴`保存`到一个`安全的地方`.以备下次登录时不用再次生成.
   
   
3. 在 `Root shell - interactive` 页面, 点击 `Launch` 按钮. 就进入了 `Linux` 的字符界面了.

    <img src="ssr/root-shell.png" />

4. 在出现的 `Linux` 登录界面上, 请在 `host login:` 后面键入账号名 `root` 并回车. 
    在随后出现的 `Password:` 后摸黑键入上面生成的密码并回车.
    如果出现下图的界面, 表明成功登录 Linux 主机.
    
    > 注: 搬瓦工早期提供的 Linux 系统不需要登录, 这一步就略过了. 
    
    <img src="ssr/root-login.png" />
    
5. 现在, 开始安装 `SSR` 的流程. 请逐行键入以下命令并回车, 不要复制粘贴, 否则吃不了兜着走. 
    
    > 注意, 下列命令中从`井号`到`行末`的内容是注释, 不要输入(没中文输入法, 想输也输不了).
    
```bash
sudo su                               # 将当前账号的权限提升到超级用户
cd /                                  # 将当前工作路经切换到根目录
yum install git -y                    # 安装 git 软件
git clone https://github.com/koolshare/shadowsocksr.git  # 用 git 命令拉取 SSR 源代码
cd shadowsocksr                       # 进入 SSR 软件目录
sh ./initcfg.sh                       # 执行 SSR 配置文件的初始化, 这一步将创建 user-config.json 配置文件
vi /shadowsocksr/user-config.json     # 运行 vi 编辑器修改配置文件. 下文专开一节详述
vi /etc/rc.local                      # 运行 vi 编辑器修改或创建 Linux 自启动脚本文件 rc.local
chmod +x /etc/rc.local                # 为 自启动脚本文件 rc.local 添加 可执行文件 属性
reboot                                # 配置完毕后, 重启 Linux 主机
```
