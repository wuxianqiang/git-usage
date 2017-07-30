# git 使用说明

1. 删除远程分支
> git push origin --delete 分支名

2. 删除本地分支
> git branch -d 分支名

3. 重命名本地分支
> git branch -m 原分支名 新分支名

4. 推送本地分支
> git push origin 分支名

5. 查看远程分支
> git branch -a

6. 查看本地分支
> git branch

7. 新建本地分支
> git branch 分支名

8. 切换本地分支
> git checkout 分支名

9. 重命名远程分支
> 在git中重命名远程分支，其实就是先删除远程分支，然后重命名本地分支，再重新提交一个远程分支。

10. 根据远程分支创建本地分支
> git checkout -b 分支名 origin/分支名
