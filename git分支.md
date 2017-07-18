# 分支的新建与合并

* 分支的新建与切换

git branch [branch-name]  --新建分支（在当前commit上新建新建一个分支指针）

git branch checkout [branch-name]  --切换分支

*注：git checkout -b [branch-name]  --新建并切换分支*

* 分支的删除

 git branch -d [branch-name]
 
* 分支的合并

git merge [branch-name] (将当前分支合并到master分支)

**注：如果master分支是待合并分支的直接祖先，合并将采用快进模式（直接移动HEAD指针），否则将新建一个合并对象**

* 遇到冲突时的分支合并

*如果在不同分支中修改了同一文件的同一部分，将会产生冲突。*

**当使用 git merge 进行合并时，git会进行合并，但是不会进行提交，而是等待解决冲突**
**使用 git status 可以查看到标记为 unmerged path 的文件（即包含冲突的文件，需要手动解决）**
**冲突文件由======分割，保留其一便可解决冲突**
**在解决了所有文件里的所有冲突后，运行 git add 将把它们标记为已解决状态（译注：实际上就是来一次快照保存到暂存区域。），git commit 提交合并**

# 分支的管理

* 分支的管理

git branch --列出分支清单

*分支前的 * 字符：它表示当前所在的分支*

 git branch -v --查看各个分支最后一个提交对象的信息
 
 git branch --merged(or --no--merged) --查看已经合并（未合并）的分支
