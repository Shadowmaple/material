# 添加源

> [参考文档](https://www.jianshu.com/p/57a91bc0c594)

## 什么是软件源?
源,在Ubuntu下,它相当于软件库,需要什么软件,只要记得正确的软件名就可以用命令安装：
'sudo apt-get install [软件名]'

## 软件源的分类
在 Ubuntu 中软件源其实还细分为下面两种：

1. Ubuntu 官方软件源
2. PPA 软件源
	PPA 源，就是指 “Personal Package Archives” ，也就是个人软件包集。这其实是一个网站，即－launchpad.net。Launchpad 是 Ubuntu 母公司 Canonical 有限公司所架设的网站，是一个提供维护、支援或联络 Ubuntu 开发者的平台。由于不是所有的软件都能进入 Ubuntu 的官方的软件库，launchpad.net 提供了 PPA，允许开发者建立自己的软件仓库，自由的上传软件。供用户安装和查看更新。


## 为什么要替换系统默认的官方软件源？
因为 Ubuntu 的官方软件源的服务器是在国外，而从我们中国访问国外的网站都必须先经过一堵“墙”来验证这个网站是否可以访问，另外一个原因就是服务器在国外，距离远了，访问的速度当然没有直接访问国内的网站快。正是由于这种的访问检查和网络传输距离问题，导致我们通常访问 Ubuntu 官方软件源的速度很慢。因此需要替换官方源。


## 修改官方源
Ubuntu 官方软件源中包含了 Ubuntu 系统中所用到的绝大部分的软件，它对应的源列表是 `/etc/apt/sources.list`。只需要修改这个文件，就能添加我们想要的源。修改操作：
+ `sudo vi /etc/apt/sources.list`
+ `sudo apt-get update` 要记得刷新一下

> 国内开源镜像站点汇总：https://segmentfault.com/a/1190000000375848


# [切换为zsh](https://github.com/Shadowmaple/something_for_ubuntu/blob/master/zsh.md)


