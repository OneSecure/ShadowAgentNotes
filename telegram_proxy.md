# Telegram 代理服务器 搭建 图文教程

Telegram(简称 TG 或者 电报) 在咱 `兲朝上国` 是不能直接访问的. 

目前 TG 由于自身某些原因, 即使在全局 `翻墙` 的状态下, 也不能访问.

因此, 自己搭建 TG 独家支持的 `MTProto` 协议的代理服务器, 一劳永逸地支持所有平台和设备, 就显得很有必要了.

## 购买 VPS, 创建公网虚拟主机
参看 [vultr 主机 教程](vultr.md#创建虚拟主机) 

## 部署 `MTProto` 代理服务器
- 经过测试, 由 `TG` 社区提供的 c 语言[版本](https://github.com/TelegramMessenger/MTProxy) 有严重问题, CPU 占用率长期畸高, 还可能偷跑大量流量, 费用账单会直接把你吓尿. 因此不要使用.
- 网络上的替代品是 python3 版的 [Async MTProto Proxy](https://github.com/alexbers/mtprotoproxy). 它 几乎不占 CPU, 表现平稳, 相当令人满意.

### 准备工作
- 下列命令中从 `井号` 到行末的内容是注释, 不要输入.
```bash
sudo su  # 将当前账号的权限切换到超级用户(switch user, 简写为 su)
cd /     # 将当前工作路径切换到根目录, 注意 cd 和 斜杠 之间的 空格 别漏了.
```

### 安装 python3 
- 由于 `CentOS` 7 及以下系统并不搭载 `python3`, 用户得自己安装, 参考[这个文章](https://www.scivision.co/python3-centos-install/), 执行作者提炼出的如下几个命令 即可装上. 
- 当然, 其它系统如 `Ubuntu` 等已经搭载了 `python3` 的, 可以跳过这一步.
```bash
yum install https://centos7.iuscommunity.org/ius-release.rpm -y
yum update -y
yum install python36u python36u-pip -y
ln -s /opt/rh/rh-python36/root/usr/bin/python /usr/bin/python3
```
- 装好以后敲入 `python3` 命令验证一下. 然后在 `python3` 环境控制台上敲入 `quit()` 语句退出 `python3` 环境.

### 安装 git
- CentOS / Fedora / RHEL
```bash
yum install git -y
```
- Ubuntu / Debian
```bash
apt-get install git -y
```

### 安装 Async MTProto Proxy 服务器

1. 获取 `Async MTProto Proxy` 源代码
```bash
git clone -b stable https://github.com/alexbers/mtprotoproxy.git
```

2. 编辑配置文件

首先用如下命令生成密钥
```bash
head -c 16 /dev/urandom | xxd -ps
```
作者得到的密钥是 `a843b0aaf852b611dff4024a3a1e0f86`

再用 vi 命令编辑 `config.py` 文件
```bash
vi /mtprotoproxy/config.py
```
编辑后的文件去掉了多余的内容, 如下图.
```
PORT = 4567
USERS = {
    "tg2": "a843b0aaf852b611dff4024a3a1e0f86"
}
```
其中 `port` 的值是监听端口, 下一条语句是 `密钥` 值.

3. 运行  代理服务器
```bash
python3 /mtprotoproxy/mtprotoproxy.py &
```
