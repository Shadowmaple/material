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

+ `select-editor` 修改默认编辑器
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


## 打开文件或其它
+ `xdg-open`	选择系统默认程序打开文件
+ `eog xxx.bmp &`	打开图片
+ `evince xxx.pdf &`	打开pdf文件
+ `gedit`		打开文档
+ `nautilus &`	打开文件管理器

## 打开浏览器
+ 火狐：`firefox &`
+ 谷歌：`google-chrome &`

