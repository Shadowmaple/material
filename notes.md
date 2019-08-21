# 终端窗口操作

| 操作 | 效果 |
| --- |:---:	|
| Shift+Ctrl+T　|　新建标签页 |
|Shift+Ctrl+W　|　关闭标签页 |
|Ctrl+PageUp　|　前一标签页 |
|Ctrl+PageDown　|　后一标签页 |
|Shift+Ctrl+PageUp |　标签页左移 |
|Shift+Ctrl+PageDown　|　标签页右移 |
|Alt+1　|　切换到标签页 |
|Shift+Ctrl+N　|　新建窗口 |
|Shift+Ctrl+Q　|　关闭终端 |
| ctrl+shift+C | 复制(同理粘贴剪切)|
|Ctrl + l | 清屏 |

___


# 命令行Command

+ `history`	显示命令历史记录列表
	+ `history num`		最近num条命令
	+ `!num`			执行第num个历史命令
+ `clear/ctrl-l`		清屏
+ `reset`			刷新 shell 提示屏幕
+ `pwd`			当前路径
+ `free -h`			查看内存状态
+ `sudo update-alternatives --config editor`	修改默认编辑器
+ `diff a b`	比较a和b的不同，a,b为文件或目录
+ `chmod`	修改文件(夹)许可
	+ ex：`chmod 756 code`	code为一目录
	+ ps：rwx——421；700——rwx(user),r-x(group),r--(others)
	+ ex：`chmod u-x code` 	取消code文件夹下uesr的executable(可执行)许可
	+ ps：a-all, g-group, ... ; +/- ——添加/取消
+ `ls`/`l`
	+ `ls -a`/`la`	列出所有目录，包括隐藏
	+ `ls -l`/`ll`	列出目录且包括属性
	+ `ll`			列出所有目录且包括属性
+ `tree`	将文件（夹）以树状图的方式显示
	+ tree dic	单独显示目录dic
+ d
  zsh，显示最近的历史记录（目录）
+ zsh_stats
  zsh，看到你的使用频率前 20 的命令是什么


## 打开文件或其它
+ `xdg-open`	选择系统默认程序打开文件
+ `eog xxx.bmp &`	打开图片
+ `see xx.png` 打开图片
+ `evince xxx.pdf &`	打开pdf文件
+ `gedit`		打开文档
+ `nautilus &`	打开文件管理器

## 打开浏览器
+ 火狐：`firefox &`
+ 谷歌：`google-chrome &`

# 进入root模式
输入
```
su
```
输入root用户的密码即可

输入`exit`回到用户权限

# linux 截屏
+ PrtScn ：捕获全屏画面。捕获的图片会显示整个屏幕上的画面。
+ Alt + PrtScn： 捕获窗口画面，这个快捷键可以创建当前活跃窗口的截图。
+ Shift + PrtScn：选择需要捕获的画面，你可以点击并拖拽选择框来确定捕捉的画面。

# 批量删除进程
```shell
$ kill -9 `ps -ef | grep xxx | awk '{print $2}' `
# 或者
$ killall xxx
```

# 磁盘内存信息

- `df -h`
  列出文件系统的整体磁盘使用量
- `du -h`
  以易读方式列出当前目录下所有文件容量
- `du -s`
  仅列出当前目录的文件总量
- `du -sh /*`
  检查根目录下每个目录所占的容量
- `lsblk`
  列出系统上的所有磁盘列表
- `parted`
  列出磁盘的分区表类型与分区信息