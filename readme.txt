<<<<<<< HEAD
git commit --amend
git rebase -i parent-ID
git diff --cached  暂存区和HEAD的区别
git diff           暂存区和工作区的区别
git diff -- <filename..> 仅仅比较工作区和暂存区的某个(几个)文件的差别
git diff branch-name1 branch-name2 比较两个分支的所有文件的区别
git diff branch-name1 branch-name2  --<filename..> 比较两个分支的具体文件的差异
git checkout -b name ID
git branch -av
git checkout name
git branch -d name
git reset HEAD      将添加到暂存区中的文件取消,恢复到工作区
git reset HEAD -- <filename..> 将暂存区的部分文件恢复为HEAD
git reset --hard commit-ID 将工作区,暂存区,仓库,恢复到commit-id所对应的状态
git rm <filename> 删除指定文件  通过reset 可以恢复回来
git checkout -- filename..  将工作区中的某文件恢复成为暂存区文件
git stash 将当前进度的工作状态储存
git stash list 查看stash中储存的存档
git stash pop  将stash中储存的存档pop出来<恢复处理到一半的工作>
git stash apply 将stash中储存的存档复制一份出来<恢复处理到一半的工作>
git clone --bare /xxx/xxx/xxx/xxx.git name.git    以哑协议克隆仓库得到备份
git clone --bare file:///xxx/xxx/xxx/xxx.git name.git 以智能协议克隆仓库得到备份
git remote -v 查看当前仓库的remote
git remote add name file:///xxx/xxx/xxx/xxx.git  将备份仓库和当前仓库进行remote
创建ssh ssh-keygen -t rsa -b 4096 -C "gmliyanfeng@gmail.com"
查看创建的公钥 cat ~/.ssh/id_rsa.pub
git marge name/branch-name  将当前分支和远端的某个分支左merge操作,生成一个将当前branch和远端branch均作为parents的节点
基于远端分支创建本地分支 git checkout -b 本地-branch-name 远端-branch-name 
-------------------------------------------------------------------------
-------------------------------------------------------------------------
当出现nan-fast-forward的时候是本地分支和远端分支不匹配的原因,需要fetch下来进行merge
或者经行pull

<<<<<<< HEAD

添加冲突  from GITliyanfeng

=======
添加一个冲突
>>>>>>> fa43ab4

同一分支,在同一个文件的不同位置,或者不同文件中,两个客户端分别做了修改,而且其中以一先提交到远端仓库,那么后提交的那个需要先将远端fetch,然后再merge,最后再能提交到远端仓库

同一个分支,在同一个文件的相同位置,两个客户端分别做了修改而产生冲突,而且有一个客户端先提交到了远端仓库,那么后提交的需要先将仓库poll,然后手动调整冲突的位置,然后形成一个commit,最后才能push到远端仓库

当同一个分支的两个客户端,一个进行了文件名修改并提交到远端,另一个在旧的文件名文件中修改了内容,后者无法push到远端,这个时候,后者就需要先进行pull,git会自动的将新文件同步下来,并且将在旧文件中更改的内容写入到新文件中,这个时候再进行push就可以了
