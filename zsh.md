# 切换为zsh

# zsh简介
zsh是一个Linux下强大的shell, 由于大多数Linux产品安装，以及默认使用bash shell, 但是丝毫不影响极客们对zsh的热衷,几乎每一款Linux产品都包含有zsh，通常可以用apt-get、urpmi或yum等包管理器进行安装

## zsh的主要功能

+ 开箱即用、可编程的命令行补全功能可以帮助用户输入各种参数以及选项
+ 在用户启动的所有shell中共享命令历史
+ 通过扩展的文件通配符，可以不利用外部命令达到find命令一般展开文件名
+ 改进的变量与数组处理
+ 在缓冲区中编辑多行命令
+ 多种兼容模式，例如使用/bin/sh运行时可以伪装成Bourne shell
+ 可以定制呈现形式的提示符；包括在屏幕右端显示信息，并在键入长命令时自动隐藏
+ 可加载的模块，提供其他各种支持：完整的TCP与Unix域套接字控制，FTP客户端与扩充过的数学函数
+ 完全可定制化

# 切换操作
+  查看当前系统存在的shell环境
 
        cat /etc/shells
+ 得到当前的shell环境

        echo $SHELL
+ 在linux系统的`/etc/passwd`文件内是保存系统内所有用户和用户的设置。
对某用户的默认设置也在这里。首先我们可以查看一下当前的用户设置：

        grep [username] /etc/passwd

+ 修改某用户的默认shell
    + 可用输入`chsh`选择：
		```
        lawler@maple:~$ chsh
        Password: 
		Changing the login shell for lawler
		Enter the new value, or press ENTER for the default
				Login Shell [/bin/bash]: 
		```

    + 也可以直接一道命令

            sudo usermod -s /bin/zsh [username]
		或者

            chsh -s /bin/zsh
		或者

            chsh -s `which zsh`



+ 重启

        reboot

# oh-my-zsh
## 简介
Oh-My-Zsh是一款社区驱动的命令行工具，正如它的主页上说的，Oh-My-Zsh是一种生活方式。它基于zsh命令行，提供了主题配置，插件机制，已经内置的便捷操作。给我们一种全新的方式使用命令行。

Oh-My-Zsh这个名字听起来就很有意思，它是基于zsh命令行的一个扩展工具集，提供了丰富的扩展功能。

Oh-My-Zsh只是一个对zsh命令行环境的配置包装框架，但它不提供命令行窗口，更不是一个独立的APP。

更详细介绍可到[官网](http://ohmyz.sh)了解

## 安装
前提：已安装git
安装：

    wget https://github.com/robbyrussell/oh-my-zsh/raw/master/tools/install.sh -O - | sh


## 修改[主题](https://github.com/robbyrussell/oh-my-zsh/wiki/themes)

    vim ~/.zshrc
修改为ys

	ZSH_THEME="ys"

或者随机选择主题:

	ZSH_THEME="random"

更新配置：
        
    source ~/.zshrc

## 自动补全插件
[incr.zsh 补全插件](http://mimosa-pudica.net/zsh-incremental.html)

下载：

	wget http://mimosa-pudica.net/src/incr-0.2.zsh
将此插件放到oh-my-zsh目录的插件库下：

	mv incr-0.2.zsh .oh-my-zsh/plugins/incr
在`~/.zshrc`文件末尾加上启动命令

	source ~/.oh-my-zsh/plugins/incr/incr*.zsh
更新配置

	source ~/.zshrc

> 详见参考文档

## 提示字符的设置
### 设置
变量：PS1 或 PROMPT

```shell
# 查看当前设置
➜  ~ git:(master) ✗ echo $PS1
${ret_status} %{$fg[cyan]%}%c%{$reset_color%} $(git_prompt_info)

#添加时间并赋予紫色
➜  ~ git:(master) ✗ PS1='${ret_status} %{$fg[cyan]%}%c %{$fg_bold[magenta]%}%* $(git_prompt_info)$reset_color'
➜  ~ 16:35:31 git:(master) ✗ 
```

### 彩色设置
[参考文档](https://wiki.archlinux.org/index.php/Zsh_%28%E7%AE%80%E4%BD%93%E4%B8%AD%E6%96%87%29#.E5.BD.A9.E8.89.B2)

在 `.zshrc` 中 `PROMPT=` 前面添加 `autoload -U colors && colors` 来启用彩色提示符

### 特定符号
|code|info|
| :---:|:---:|
|%T|系统时间（时：分）
|%*|系统时间（时：分：秒）
| %D| 系统日期（年-月-日）
| %n| 你的用户名
| %B - %b | 开始到结束使用粗体打印
| %U - %u | 开始到结束使用下划线打印
| %d | 你目前的工作目录
| %~ | 你目前的工作目录相对于～的相对路径
| %M |计算机的主机名
| %m | 计算机的主机名（在第一个句号之前截断）
| %l | 你当前的tty
|%n |登录名


# 参考文档
+ [Linux终极shell-Z Shell-用强大的zsh & oh-my-zsh把Bash换掉](https://github.com/gatieme/AderXCoding/tree/master/system/tools/zsh)
+ [oh-my-zsh](https://www.jianshu.com/p/d194d29e488c?open_source=weibo_search)
+ [那些我希望在一开始使用 Zsh(oh-my-zsh) 时就知道的](https://segmentfault.com/a/1190000002658335)
+ [各类插件](https://github.com/robbyrussell/oh-my-zsh/wiki/Plugins-Overview#fs-jumping)




