git commit --amend
git rebase -i parent-ID
git diff --cached  暂存区和HEAD的区别
git diff           暂存区和工作区的区别
git diff -- <filename..> 仅仅比较工作区和暂存区的某个(几个)文件的差别
git checkout -b name ID
git branch -av
git checkout name
git branch -d name
git reset HEAD      将添加到暂存区中的文件取消,恢复到工作区
git reset HEAD -- <filename..> 将暂存区的部分文件恢复为HEAD
git checkout -- filename..  将工作区中的某文件恢复成为暂存区文件


