### 快速开始
初始化
```
git init
```
创建文件
```
touch i.js
```
提交暂存区
```
git add .
```
提交
```
git commit -m 第一次提交
```
编辑历史区
```
vi 1.js
```
再提交
```
git add commit -a -m 第二次提交
```
 创建并切换分支
```
git checkout -b dev
```
在编辑
```
vi 1.js
```
提交到哪个分支就切换到哪个分支提交
```
git add commit -a -m 第三次提交
```
切换到master分支，然后合并分支
```js
git checkout master
git merge dev
```

### 常用命令
1. 删除远程分支
```
git push origin --delete 分支名
```

2. 删除本地分支
```
git branch -d 分支名
```

3. 重命名本地分支
```
git branch -m 原分支名 新分支名
```

4. 推送本地分支
```
git push origin 分支名
```

5. 查看远程分支
```
git branch -a
```

6. 查看本地分支
```
git branch
```

7. 新建本地分支
```
git branch 分支名
```

8. 切换本地分支
```
git checkout 分支名
```

9. 重命名远程分支
```
在git中重命名远程分支，其实就是先删除远程分支，然后重命名本地分支，再重新提交一个远程分支。
```

10. 根据远程分支创建本地分支
```
git checkout -b 分支名 origin/分支名
```

11. 使用上次的提交记录
```
git commit --amend
```
12. 查看提交差异
```
git show 版本号
```

```js
i // 进入编辑模式
ESC :wq // 保存并退出
```

### 解决冲突
没有及时拉下最新代码导致冲突的解决办法
```js
git pull --reabase origin master
// 该完冲突后重新提交代码
git add .
// 重新提交不要写提交信息
git rebase --continue
// 退出
git push origin wuxianqiang2 -f
// 再次提交到远端需要强推
```

合并提交信息
```js
git rebase -i HEAD^^
// 然后在需要合并提交信息的前面加s
// 然后在需要保留提交信息的前面加#
```

因为没有在合并之前拉下最新的代码，导致同时修改同一行，合并的时候会有代码冲突，需要执行如下操作
```
1. 在你自己的分支上
2. 拉取目标分支最新代码
3. git pull --rebase origin master 
4. 查看冲突的文件
5. git status
6. 打开代码，解决冲突吧，获取没有冲突是最好的
7. 提交代码
8. git add .
9. 退出rebase环境
10. git rebase --continue
11. git push origin wuxianqiang_branch
```

### 撤销操作
git撤销本地所有未提交的更改
```
git clean -df
git reset --hard
```
第一个命令只删除所有未跟踪的文件，如果文件已经被跟踪, 修改过的文件不会被回退。而第二个命令把跟踪的文件还原到前一个版本，对于未跟踪的文件(比如编译的临时文件)都不会被删除。

撤销已提交的改动（执行这个命令要写提交信息）
```
git revert 版本号
```
使用 “git revert” 命令可以撤销某个之前的提交。但是这个命令并不是删除那个提交，相反的，它是恢复那个提交的改动，这只是看起来像是撤销而已。这个操作实际上会自动产生一个新的提交。在提交中包括了你想要撤销的那个提交的所有反向改动。例如在原始提交中，你在某一个位置添加一些字符，那么这个恢复提交（reverting commit）就会把这些字符删除掉。

另外一种撤销提交的方法是使用 “git reset” 命令。这个操作不会自动产生一个新的提交，或是删除你要撤销的提交，它会重置你当前的 HEAD 分支到一个特定旧的版本，也被称作 “回滚” 到旧的版本：
```
git reset --hard 版本号
```
### 写在最后

喜欢的小伙伴们请点一下右上脚star按钮:star:，就可以收藏这篇文章啦！，如果你有更好的前端知识需要和我一起分享，请点fork按钮，提交你的资料吧！如果想在第一时间获取我的更新，并且每次更新会有提醒，请点watch按钮。
