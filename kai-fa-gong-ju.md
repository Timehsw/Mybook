

# git 常用命令

## git 配置命令

git init                                                  \# 初始化本地git仓库（创建新仓库）

git config --global user.name "xxx"                       \# 配置用户名

git config --global user.email "xxx@xxx.com"              \# 配置邮件

ssh-keygen -t rsa -C xxx@xxx.com                 \# 生成SSH秘钥

git config --global color.ui true                         \# git status等命令自动着色

git config --global color.status auto

git config --global color.diff auto

git config --global color.branch auto

git config --global color.interactive auto

git config --global --unset http.proxy                    \# remove  proxy configuration on git

git clone git+ssh://git@192.168.53.168/VT.git             \# clone远程仓库

git status                                                \# 查看当前版本状态（是否修改）

git add xyz                                               \# 添加xyz文件至index

git add .                                                 \# 增加当前子目录下所有更改过的文件至index

git commit -m 'xxx'                                       \# 提交

git commit --amend -m 'xxx'                               \# 合并上一次提交（用于反复修改）

git commit -am 'xxx'                                      \# 将add和commit合为一步



## git 删除相关

git rm xxx                                                \# 删除index中的文件

git rm -r \*                                               \# 递归删除

git rm --cached xxx.rb                                    \# 将xxx.rb从暂存区删除,但并不从文件系统里移除,只是移出git的管理



git mv README README2                                     \# 重命名文件README为README2



## git 日志相关

git log                                                   \# 显示提交日志

git log -1                                                \# 显示1行日志 -n为n行

git log -5

git log --stat                                            \# 显示提交日志及相关变动文件

git log -p -m

git log v2.0                                              \# 显示v2.0的日志

git show dfb02e6e4f2f7b573337763e5c0013802e392818         \# 显示某个提交的详细内容

git show dfb02                                            \# 可只用commitid的前几位

git show HEAD                                             \# 显示HEAD提交日志

git show HEAD^                                            \# 显示HEAD的父（上一个版本）的提交日志 ^^为上两个版本 ^5为上5个版本

git show v2.0                                             \# 显示v2.0的日志及详细内容

git show HEAD@{5}

git show master@{yesterday}                               \# 显示master分支昨天的状态

git show HEAD~3

git show -s --pretty=raw 2be7fcb476

git tag                                                   \# 显示已存在的tag

git tag -a v2.0 -m 'xxx'                                  \# 增加v2.0的tag

git diff                                                  \# 显示所有未添加至index的变更

git diff --cached                                         \# 显示所有已添加index但还未commit的变更

git diff HEAD^                                            \# 比较与上一个版本的差异

git diff HEAD -- ./lib                                    \# 比较与HEAD版本lib目录的差异

git diff origin/master..master                            \# 比较远程分支master上有本地分支master上没有的

git diff origin/master..master --stat                     \# 只显示差异的文件，不显示具体内容

git remote add origin git+ssh://git@192.168.53.168/VT.git \# 增加远程定义（用于push/pull/fetch）



## git 分支相关

git branch testing                                        \# 创建分支testing

git checkout testing                                      \# 切换到testing分支

git checkout -b testing                                    \#创建testing分支，并切换到testing分支，是上面两个命令的合并

git log --oneline --decorate --graph --all                \# 输出你的提交历史、各个分支的指向以及项目的分支分叉情况

git branch                                                \# 显示本地分支

git branch --contains 50089                               \# 显示包含提交50089的分支

git branch -a                                             \# 显示所有分支

git branch -r                                             \# 显示所有原创分支

git branch --merged                                       \# 显示所有已合并到当前分支的分支

git branch --no-merged                                    \# 显示所有未合并到当前分支的分支

git branch -m master master\_copy                          \# 本地分支改名

git branch -d hotfixes/BJVEP933                           \# 删除分支hotfixes/BJVEP933（本分支修改已合并到其他分支）

git branch -D hotfixes/BJVEP933                           \# 强制删除分支hotfixes/BJVEP933

git show-branch                                           \# 图示当前分支历史

git show-branch --all                                     \# 图示所有分支历史

git checkout -b master\_copy                               \# 从当前分支创建新分支master\_copy并检出

git checkout -b master master\_copy                        \# 上面的完整版

git checkout features/performance                         \# 检出已存在的features/performance分支

git checkout --track hotfixes/BJVEP933                    \# 检出远程分支hotfixes/BJVEP933并创建本地跟踪分支

git checkout v2.0                                         \# 检出版本v2.0

git checkout -b devel origin/develop                      \# 从远程分支develop创建新本地分支devel并检出

git checkout -- README                                    \# 检出head版本的README文件（可用于修改错误回退）

git merge origin/master                                   \# 合并远程master分支至当前分支

git cherry-pick ff44785404a8e                             \# 合并提交ff44785404a8e的修改

## git 发布相关

git push origin master                                    \# 将当前分支push到远程master分支

git push origin :hotfixes/BJVEP933                        \# 删除远程仓库的hotfixes/BJVEP933分支

git push --tags                                           \# 把所有tag推送到远程仓库

git fetch                                                 \# 获取所有远程分支（不更新本地分支，另需merge）

git fetch --prune                                         \# 获取所有原创分支并清除服务器上已删掉的分支

git pull origin master                                    \# 获取远程分支master并merge到当前分支



git reset --hard HEAD                                     \# 将当前版本重置为HEAD（通常用于merge失败回退）

git rebase

git ls-files                                              \# 列出git index包含的文件

git whatchanged                                           \# 显示提交历史对应的文件修改

git revert dfb02e6e4f2f7b573337763e5c0013802e392818       \# 撤销提交dfb02e6e4f2f7b573337763e5c0013802e392818

git ls-tree HEAD                                          \# 内部命令：显示某个git对象

git rev-parse v2.0                                        \# 内部命令：显示某个ref对于的SHA1 HASH

git reflog                                                \# 显示所有提交，包括孤立节点

git log --pretty=format:'%h %s' --graph                   \# 图示提交日志



## git 状态相关

git stash                                                 \# 暂存当前修改，将所有至为HEAD状态.你做了一些修改并且向稍后再它们上面工作。你应该保存它们，但是不提交它们

git stash list                                            \# 查看所有暂存

git stash show -p stash@{0}                               \# 参考第一次暂存

git stash apply stash@{0}                                 \# 应用第一次暂存

git grep "delete from"                                    \# 文件中搜索文本“delete from”

git grep -e '\#define' --and -e SORT\_DIRENT



## git 更改分支名字

git branch -m old\_branch new\_branch         \# Rename branch locally   

git push origin :old\_branch                 \# Delete the old branch   

git push --set-upstream origin new\_branch   \# Push the new branch, set local branch to track the new remote



## git 查看日志

git log --pretty=oneline                                  \# 一行显示一次提交信息



## git 远程仓库

git clone https://github.com/Timehsw/LearnGit             \# 下载远程仓库

git remote -v                                             \# 显示当前的远程仓库\(简写与其对应的 URL\)

git remote                                                \# 显示当前的远程仓库\(只有简写\)

git remote add &lt;shortname&gt; &lt;url&gt;                          \# 添加远程仓库\(可以用shortname代替url的引用,也就是简写\)

git fetch \[remote-name\]                                   \# 从远程仓库中抓取与拉取

git push -u \[remote-name\] \[branch-name\]                      \# 推送到远程仓库\(eg:git push origin master\)

git remote show \[remote-name\]                             \# 查看远程仓库\(eg:git remote show origin\)

git remote rename \[shortname\] \[newname\]                   \# 远程仓库的重命名\(eg:git remote rename pb paul\)

git remote rm \[shortname\]                                 \# 远程仓库的移除\(eg:git remote rm paul\)



## git 标签

git tag                                                   \# 列出标签

git tag -a v1.0 -m "create v1.0 tag"                      \# 创建附注标签\(附注标签会包含一些标签信息\)

git show v1.0                                             \# 查看标签信息与对应的提交信息

git tag v1.1                                              \# 创建轻量标签\(轻量标签本质上是将提交校验和存储到一个文件中 - 没有保存任何其他信息\)

git tag -a v1.2 9fceb02                                   \# 后期打标签\(给之前的提交打个标签,v1.2是标签名字 9fceb02是某一次提交的hash值或者部分hash值 \)

git push origin \[tagname\]                                 \# 共享标签到远程仓库\(eg:git push origin v1.0\)

git push origin --tags                                    \# 把所有不在远程仓库服务器上的标签全部传送到那里

git checkout -b version2 v1.1                             \# 检出标签\(在特定的标签上创建一个新分支\)

Git 别名



# git 笔记

## 从 git 管理中取消

```
我们得先把idea从git的管理里撤销
git rm --cached -r .idea/
然后提交此次动作
git commit -m "rm cached .idea"
```







