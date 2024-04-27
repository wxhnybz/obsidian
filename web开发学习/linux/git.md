![[Pasted image 20231008193508.png]]
#### 主要就分为这三个区域，工作区，暂存区，提交区
在workdir中git add添加到暂存区，在暂存区中git commit放在提交区

![[Pasted image 20231008193625.png]]

* git reset 指令可以将已经add到缓存区中的修改的文件进行还原到工作区中，但是不会修改文件
* git checkout 指令可以将已经修改的文件进行还原到上一次add的状态,但是新文件并不会处理
* 在提交区中，已经乱改一通之后，git checkout HEAD .就是回到一开始的状态，移动指针
* git checkout ${HASH} ${FILE}就是将某一个文件恢复到给定hash值的版本状态。
#### 新建分支
git checkout -b newbranch oldbranch
在oldbranch上新建一个newbranch分支
git checkout ...a就是切换分支到这一个上面
如果没有oldbranch分支这一个参数,就是在当前分支上新建一个newbranch分支
#### 合并
* git rebase ${B}复制粘贴分支内容，我在a分支使用，就是复制a分支的内容到B上面,然后切换到a分支之后，git rebase ${a} 就是将两个分支合并，合并再a分支上。
* git merge ${B} 我当前在A分支上，在A分支的基础上进行合并B分支

#### 删除
* git branch 用来显示当前的所有分支
* git branch -d new 用来删除new分支，（该分支会删除，但是提交记录并不会删除）