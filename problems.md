# problems for ubuntu

ps:在应用ubuntu过程中遇到的许些问题

***
  
## *.gitignore*规则不生效的解决办法

把某些目录或文件加入忽略规则，按照上述方法定义后发现并未生效，原因是`.gitignore`只能忽略那些原来没有被追踪的文件，如果某些文件已经被纳入了版本管理中，则修改`.gitignore`是无效的。那么解决方法就是先把本地缓存删除（改变成未被追踪状态），然后再提交。命令如下：

    git rm -r --cached .
    git add .
    git commit -m 'update .gitignore'
