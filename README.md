# git-primer
----


## windos需要提前下载 gitbash
>https://git-for-windows.github.io/


>https://github-cloud.s3.amazonaws.com/releases/23216272/7830705c-71bd-11e6-946b-88a3a412ab2f.exe?X-Amz-Algorithm=AWS4-HMAC-SHA256&X-Amz-Credential=AKIAISTNZFOVBIJMK3TQ%2F20160923%2Fus-east-1%2Fs3%2Faws4_request&X-Amz-Date=20160923T150614Z&X-Amz-Expires=300&X-Amz-Signature=f604a7b80b7c086ac1b9875d8657dba392ec95e30d593ae3ff4f40315a09ac16&X-Amz-SignedHeaders=host&actor_id=10740524&response-content-disposition=attachment%3B%20filename%3DGit-2.10.0-64-bit.exe&response-content-type=application%2Foctet-stream


>git config --global user.email "NoBey@nobey.cn"

>git config --global user.name "NoBey"


## github 免密码

>ssh-keygen -t rsa -P ''

生成 密钥

找到~./ssh/id_rsa.pub

把内容添加到 github设置的SSH keys


## git 设置不提交 .gitignore

通过修改全局配置 `git config` 中的 `excludesfile` 指定全局忽略文件。设置方法：

>git config --global core.excludesfile ~/.gitignore

实际项目中，很多文件都是不需要版本管理的，比如Python的.pyc文件和一些包含密码的配置文件等等。

`/mtk/` 过滤整个文件夹

`*.zip` 过滤所有.zip文件

`/mtk/do.c` 过滤某个具体文件

需要注意的是，gitignore还可以指定要将哪些文件添加到版本管理中：

`!*.zip`

`!/mtk/one.txt`

什么要有两种规则呢？想象一个场景：我们只需要管理/mtk/目录中的one.txt文件，这个目录中的其他文件都不需要管理。那么我们就需要使用：

`/mtk/`

`!/mtk/one.txt`

配置语法：

　　以斜杠`/`开头表示目录；

　　以星号``*``通配多个字符；

　　以问号``?``通配单个字符

　　以方括号``[]``包含单个字符的匹配列表；

　　以叹号``!``表示不忽略(跟踪)匹配到的文件或目录

　　此外，git 对于 .ignore 配置文件是按行从上到下进行规则匹配的，意味着如果前面的规则匹配的范围更大，则后面的规则将不会生效；
