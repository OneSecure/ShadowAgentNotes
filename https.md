# 全免費 HTTPS 網站 搭建 詳細 图文教程

## 索引
- [Nginx 安装配置](#nginx-安装配置)


可能許多人都想過搭建個人網站玩玩，但各種嚇人門檻讓有心探索的人裹足不前。這個搭建過程就值得写写了。
搭建完成的玩具网站是有 `独立域名`, 支持 `HTTPS` 协议的哟. 
会让您有满满的成就感. 也是您进一步建设正经网站的基础.

本文假設您 
- 已經擁有了 VPS(Virtual Private Server 虚拟专用服务器), 
- 知道怎么登录远程虚拟主机, 
- 具有基本的 `linux` 命令操作经验,
- 远程主机的操作系统是 `CentOS 6.x+`.

如果您尚不具备, 请参看 [Vultr 教程](vultr.md).


## Nginx 安装配置

<img src="https://www.nginx.com/wp-content/uploads/2019/01/logo.svg" />

`Nginx`("engine x") 是由俄罗斯的程序设计师 `Igor Sysoev` 开发的高性能 `Web` 和 `反向代理` 服务器软件, 也是一个 IMAP/POP3/SMTP 代理服务器. 在高连接并发的情况下, `Nginx` 是 `Apache` 服务器不错的替代品.

### 安装编译工具及库文件
```
yum -y install make zlib zlib-devel gcc-c++ libtool  openssl openssl-devel
```

### 首先要安装 PCRE
PCRE 作用是让 Nginx 支持 Rewrite 功能。

- 下载 PCRE 安装包
```
cd /usr/local/src/
wget http://downloads.sourceforge.net/project/pcre/pcre/8.35/pcre-8.35.tar.gz
```  
![tu](https/nginx1.png)

- 解压安装包
```
tar zxvf pcre-8.35.tar.gz
```
- 进入安装包目录
```
cd pcre-8.35
```
- 编译安装 
```
./configure
make && make install
```
- 查看pcre版本
```
pcre-config --version
```
![tu](https/nginx1.png)

### 安装 Nginx



