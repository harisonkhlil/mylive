# Git 重要笔记

`git reset`版本回退，**参数 HEAD 和^表示回退到哪一版，也可以用具体版本号的头几位表示**

`git reflog`可以查看对版本的操作记录，包括被操作版本的版本号

`Working directory` and `stage(index)`

![来源为廖雪峰官方网站git教程](https://i.imgur.com/QPPcejP.jpg)

`git add` 把文件从工作区>>暂存区

`git commit`把文件从暂存区>>仓库

`git diff` 查看工作区与暂存区差异

`git diff HEAD` 查看工作区与仓库差异

`git diff --cached` 查看暂存区与仓库差异

`git diff` 如果空白,则还没有进行`git add`git diff 只显示已被 add 到版本库中的文件，在工作区和暂存区中的内容差异，所以没有显示是因为还没有 add，即使是新建的文件。您可以执行下`git status`看一下区别。

情况一. 在工作区做了修改,没有 add 想要撤消修改用`git restore filename`

情况二.在工作区进行了修改,并且 add 了,想要撤消这个 add(文件没有被修改) 用`git restore --staged file`

情况三.在工作区进行了修改,并且 add commit,想要撤消这个 add commit 用`git reset --hard HEAD^` **这样会把工作区进行的修改抹除**

==`git rm test.txt` 相当于是删除工作目录中的 test.txt 文件,并把此次删除操作提交到了暂存区==

`git checkout -- <delete file>` 丢弃暂存区该次删除操作

分支之间的跳转，需要保证该分支下工作区、暂存区与分支提交相同，无修改：即 git diff HEAD 无差异；否则在分支跳转时会出现报错情况，无法跳转

分支跳转完成后后，工作区目录会恢复到当前分支最近一次提交下的目录情况，即不同分支底下的目录内容即便存在差异，也不会互相干扰泾渭分明。

==主分支修改后没有提交是无法切换到另一分支的==

## git merge 的参数--ff、--no-ff 和–squash 的区别？

使用条件: 节点的 tag 不存储在 refs/tags/ 中时，默认使用 --no-ff。其他情况默认使用 --ff

![compare -ff and --no-ff](https://res.cloudinary.com/practicaldev/image/fetch/s--zRZ0x2Vc--/c_limit%2Cf_auto%2Cfl_progressive%2Cq_66%2Cw_880/https://dev-to-uploads.s3.amazonaws.com/i/rf1o2b6eduboqwkigg3w.gif)

`–squash` ：将待合并分支的最后一个提交放到当前分支的工作区。如 A、B、C 对 readme.tx t 进行了修改，那么–squash 的作用就是将经过 A、B、C 的 readme.txt 文件复制到工作区中。然后我们就可以进行 add 和 commit 来生成一个提交。生成的这个提交，就相当于对 A、B、C 工作的总结。

如果复制到工作区的 readme.txt 文件与工作区中的 readme.txt 文件有冲突？？答：出现这种冲突时的处理办法就是将冲突内容全部展示在 readme.txt 中。

`–squash` 只是为让提交的日志看起来简洁一些。

### collaboration

- 查看远程库信息，使用`git remote -v`；
- 本地新建的分支如果不推送到远程，对其他人就是不可见的；
- 建立本地分支，使用`git branch branch-name`, 然后推送分支.
- 从本地推送分支，使用`git push origin branch-name`，如果推送失败，先用`git pull`抓取远程的新提交；
- 建立本地分支和远程分支的关联，使用`git branch --set-upstream branch-name`；
- 从远程抓取分支，使用`git pull`，如果有冲突，要先处理冲突。
- 删除远程库，使用`git push origin --delete branch-name`

### Rebasing

git rebase 从当前分支复制提交，并将这些复制的提交放在指定分支的顶部。
如图所示：
![origin from Lydia Hallie](https://res.cloudinary.com/practicaldev/image/fetch/s--EIY4OOcE--/c_limit%2Cf_auto%2Cfl_progressive%2Cq_66%2Cw_880/https://dev-to-uploads.s3.amazonaws.com/i/dwyukhq8yj2xliq4i50e.gif)
`rabase` 是一个对主分支进行的操作.
`rabase` 是一个可以交互的操作

对正在`rebase`的 commit 有多个操作

- reword: 更改提交消息
- edit: 修改此次提交
- squash: 融合 dev 分支的最后一个 commit 到 master 分支的 HEAD
- fixup: 将提交合并到前一个提交中
- exec: 对每一个 commit 执行一个命令
- drop: 删除 commit

`drop`:
![drop](https://res.cloudinary.com/practicaldev/image/fetch/s--P6jr7igd--/c_limit%2Cf_auto%2Cfl_progressive%2Cq_66%2Cw_880/https://dev-to-uploads.s3.amazonaws.com/i/msofpv7k6rcmpaaefscm.gif)
`squash`:
![squash](https://res.cloudinary.com/practicaldev/image/fetch/s--VSQt4g1V--/c_limit%2Cf_auto%2Cfl_progressive%2Cq_66%2Cw_880/https://dev-to-uploads.s3.amazonaws.com/i/bc1r460xx1i0blu0lnnm.gif)

### Fetching

如果我们有一个远程仓库，它有我们本地分支没有的 commit .
或许我们可以使用`git fetch`
![fetch](https://res.cloudinary.com/practicaldev/image/fetch/s--38PuARw2--/c_limit%2Cf_auto%2Cfl_progressive%2Cq_66%2Cw_880/https://dev-to-uploads.s3.amazonaws.com/i/bulx1voegfji4vwgndh4.gif)
在拉取代码过程中，git fetch 会首先检查本地仓库和远程仓库的差异，检查哪些不存在于本地仓库，然后将这些变动的提交拉取到本地。
但是，这里请注意，它是把远程提交拉取到本地仓库，而不是本地工作目录，它不会自行将这些新数据合并到当前工作目录中，我们需要继续执行 git merge 才会把这些变动合并到当前工作目录。
`git pull` 和 `git fetch`的区别：
pull 根据不同配置，可等于 fetch + merge 或 fetch + rebase.
