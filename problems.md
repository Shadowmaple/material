# problems for ubuntu

ps:在应用ubuntu过程中遇到的许些问题

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
+ 解决办法：`rm -rf ~/.cache/ibus/libpingin`
+ 当然这只是治标的方法，以后还会再次出现，想要完全避免的话只能换输入法了

