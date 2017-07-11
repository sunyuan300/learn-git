# 获取项目仓库

* 在工作目录中创建仓库

> git init

* 从现有仓库克隆

> git clone [url]

    $ git clone git://github.com/sunyuan300/learn git
    
克隆learn git 到到当前工作目录下（克隆所有版本）

>　git clone [url] name

将项目重命名为name
-----
# 记录每次更新到仓库

* 检查当前工作目录状态

> git status

* 跟踪新文件

> git add [file]

git add 不仅仅可以跟踪新文件，还可以将已跟踪的文件放入缓存区

* 查看文件修改

> git diff [file]

> git diff #比较工作目录（working）与缓存区（stage）
> git diff --cache #比较缓存区域（stage）与版本库中的最新版本
> git diff HEAD #比较工作目录（working）与版本库中的最新版本

* 提交更新

> git commit

这种方式会启动文本编辑器以便输入本次提交的说明。

> git commit -m 

另外也可以用 -m 参数后跟提交说明的方式，在一行命令中提交更新

* 跳过缓存区，直接提交

> git commit -a

Git会自动把所有已经跟踪过的文件暂存起来一并提交，从而跳过 git add 步骤。

* 移除文件

> git rm [file]

同时删除缓存区（stage）和工作目录（working）下的文件，然后在提交更新。

如果是先从工作目录（working）中删除文件，然后再使用git add/rm [file]删除缓存区（stage）文件，最后提交更新。

> git rm --cache [file]

仅从缓存区（stage）删除文件，不删除工作目录（working）中的文件，即不再跟踪此文件。

* 移动文件

> git mv [name] [newname]

使工作目录（working）与缓存区中的文件都重命名，然后提交更新。

* 如果先在工作目录中更名，git 会认为删除了原来的文件，然后创建一个新的文件。 *
