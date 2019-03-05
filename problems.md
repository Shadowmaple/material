# Problems for ubuntu

在应用ubuntu过程中遇到的许些问题

***
  
## *.gitignore*规则不生效的解决办法

把某些目录或文件加入忽略规则，按照上述方法定义后发现并未生效，原因是`.gitignore`只能忽略那些原来没有被追踪的文件，如果某些文件已经被纳入了版本管理中，则修改`.gitignore`是无效的。那么解决方法就是先把本地缓存删除（改变成未被追踪状态），然后再提交。命令如下：

    git rm -r --cached .
    git add .
    git commit -m 'update .gitignore'

## 修改双系统引导顺序

因为我用的是win+ubuntu的双系统，而ubuntu是之后安装的，因此在一开始进入开机引导界面时以ubuntu为默认选项。因为我的ubuntu是安装在机械硬盘上的，开机时间十分长，极不方便，因此我需要将默认选项修改为windows。

1. 打开终端（ctrl+Alt+T）
2. 输入`sudo gredit /etc/default/grub`
3. 在文本编辑器gredit中
+ `GRUB_DEFAULT=0`代表默认启动项为第0项，若win为第三项，则改为2
+ `GRUB_TIMEOUT=10`代表选择时间(秒)
4. 修改完成退出后，执行`sudo update-grub`，以更新修改

## ibus输入法的bug

+ 描述：切换中文输入时，键入拼音，按下数字键以选择候选字，但得到的却是键入的数字
+ 解决办法
	+ `rm -rf ~/.cache/ibus/libpingin`
	+ 重启，`shutdown -r now`
+ 当然这只是治标的方法，以后还会再次出现，想要完全避免的话只能换输入法了，如搜狗

## 误入tty4界面

+ 进入：Ctrl+Alt+F4
+ 离开：Ctrl+Fn+Alt+F1（或F7、F8）

## The package system is broken
安装软件的时候出现错误，遇到包管理系统损坏的问题，可能是之前`apt upgrade`的时候，中途强制停止升级，导致系统包安装不完全。

解决方法：

强制安装未下载完成的文件包
```
sudo apt-get -f install
```
然后更新
```
sudo apt-get update
```

## `xxx is not in the sudoers file.This incident will be reported.`
[参考原地址](http://www.cnblogs.com/xiaochaoyxc/p/6206481.html)

切换到root用户

	su

添加sudo文件的写权限

	chmod u+w /etc/sudoers

编辑sudoers文件

	vi /etc/sudoers

在`root ALL=(ALL) ALL`下面添加`xxx ALL=(ALL) ALL`

撤销sudoers文件写权限

	chmod u-w /etc/sudoers

|添加方案|效果|
|:---:|:---:|
|`youuser  ALL=(ALL) ALL`           |允许用户youuser执行sudo命令(需要输入密码)              |
|`%youuser ALL=(ALL) ALL`           |允许用户组youuser里面的用户执行sudo命令(需要输入密码)  |
|`youuser  ALL=(ALL) NOPASSWD: ALL` |允许用户youuser执行sudo命令,并且无需输入密码           |
|`%youuser ALL=(ALL)  NOPASSWD: ALL` |允许用户组youuser内的用户执行sudo命令,并无需输入密码  |


