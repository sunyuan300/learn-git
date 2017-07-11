# 查看提交历史

* 查看提交历史

      git log

默认不用任何参数的话，git log 会按提交时间列出所有的更新，最近的更新排在最上面。

    -p    按补丁格式显示每个更新之间的差异。
  
    --word-diff	按 word diff 格式显示差异。
  
    --stat	显示每次更新的文件修改统计信息。
  
    --shortstat	只显示 --stat 中最后的行数修改添加移除统计。
  
    --name-only	仅在提交信息后显示已修改的文件清单。
  
    --name-status	显示新增、修改、删除的文件清单。
  
    --abbrev-commit	仅显示 SHA-1 的前几个字符，而非所有的 40 个字符。
  
    --relative-date	使用较短的相对时间显示（比如，“2 weeks ago”）。
  
    --graph	显示 ASCII 图形表示的分支合并历史。
  
    --pretty	使用其他格式显示历史提交信息。可用的选项包括 oneline，short，full，fuller 和 format（后跟指定格式）。
  
* 限制输出长度

      -(n)	仅显示最近的 n 条提交。
    
      --since, --after	仅显示指定时间之后的提交。
    
      --until, --before	仅显示指定时间之前的提交。
    
      --author	仅显示指定作者相关的提交。
    
      --committer	仅显示指定提交者相关的提交。
    
----------------

# 撤消操作

* 丢弃工作目录(working)修改

      git checkout -- [file]
    
* 撤销缓存区（stage）修改

      git reset [file]
      
**git reset 也可以用于退回版本**

      git reset HEAD^ or git reset 628de25
      
-------

# 远程仓库的使用

* 查看远程仓库

      git remote    (-v 显示对应的克隆地址)
      
* 添加远程仓库

      git remote add [shortname] [url]
      
* 从远程仓库抓取数据

      git fetch [remote-name]
      
**此命令会到远程仓库中拉取所有你本地仓库中还没有的数据。运行完成后，你就可以在本地访问该远程仓库中的所有分支,
fetch 命令只是将远端的数据拉到本地仓库，并不自动合并到当前工作分支。**

**如果设置了某个分支用于跟踪某个远端仓库的分支，可以使用 git pull 命令自动抓取数据下来，然后将远端分支自动合并到本地仓库中当前分支。**

**实际上，默认情况下 git clone 命令本质上就是自动创建了本地的 master 分支用于跟踪远程仓库中的 master 分支（假设远程仓库确实有 master 分支）。
所以一般我们运行 git pull，目的都是要从原始克隆的远端仓库中抓取数据后，合并到工作目录中的当前分支。**

* 推送数据到远程仓库

      git push [remote-name] [branch-name]
      
* 查看远程仓库信息

       git remote show [remote-name]
       
* 重命名和删除远程仓库

      git remote rename [old-name] [new-name]
      git remote rm [remote-name]
      
--------

# 打标签

* 显示已有的标签

      git tag
      
* 新建含附注的标签（保留相关信息）

      git tag -a [tag-name] -m "information"     (注：-a是  annotated的首字母)
      
* 新建轻量级标签

       git tag [tag-name]
       
* 后期加注标签

       git tag -a [tag-name] <commit>
       
* 分享标签
  
       git push [remote-name] [tag-name]
       git push [remote-name] --tags  (一次推送所有本地新增的标签)
