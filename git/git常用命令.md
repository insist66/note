### git常用命令

```js
git status (查看当前状态)
git add . (将所有更改的文件添加到暂存区域)	
git commit -m ‘xxxx’ (添加文件更改描述)
git reset --soft HEAD^ (撤销暂存)
git push (提交到仓库)
git branch 分支名 (创建新分支)
git checkout 分支名 (切换分支)
git branch (查看本地所有分支)
git branch -r (查看所有的分支)
git push origin demo:demo (将分支提交到仓库 demo分支的名字demo文件名)
git merge master (把主分支的代码merge到自己的分支)
```

### git创建新的分支无法拉取代码的问题

```js
报错如下：
$ git pull 

There is no tracking information for the current branch.
Please specify which branch you want to merge with.
See git-pull(1) for details.

    git pull <remote> <branch>

If you wish to set tracking information for this branch you can do so with:

    git branch --set-upstream-to=origin/<branch> b
```

这时候直接执行：git branch --set-upstream-to=origin/远程分支的名字 再pull就行了

### git打tag流程

```js
git tag (查看tag)

创建tag对象
git tag -a 1.0.2.20210726 -m ‘release 1.0.2’ (打tag) (1.0.2是版本号、0726日期)

把tag推送到远端仓库
git push origin 1.0.2.20210726

如果tag打错了，要删除本地和远程的版本号，再重新tag，步骤：
1、git tag -d 版本号 (删除本地tag)
2、git push origin :refs/tags/要删除的远程版本号(例如：2.3.9.20210402)
```

