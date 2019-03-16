---
layout: wiki
title: Git
categories: Git
description: Git 常用操作记录。
keywords: Git, 版本控制
---

## 常用命令

|类型  | 功能                         | 命令                                        |
|:-----|:-----------------------------|:--------------------------------------------|
|基础  | 查看状态                     | git status                                  |
|基础  | 查看分支                     | git branch -[v/vv]                          |
|基础  | 创建分支                     | git branch banchname                        |
|基础  | 切换分支                     | git checkout branchname                     |
|基础  | 添加文件/更改到暂存区        | git add filename                            |
|基础  | 添加所有文件/更改到暂存区    | git add .                                   |
|基础  | 提交修改                     | git commit -m 'msg'                         |
|基础  | 修改上次 commit              | git commit --amend                          |
|基础  | 查看配置信息                 | git config --list                           |
|缓存  | 暂存当前修改                 | git stash                                   |
|缓存  | 读取上次暂存                 | git pop                                     |
|比较  | 比较工作区和暂存区           | git diff                                    |
|比较  | 比较暂存区和版本库           | git diff --cached                           |
|比较  | 比较工作区和版本库           | git diff HEAD                               |
|修改  | 从暂存区移除文件             | git reset HEAD filename                     |
|修改  | 撤销已修改的文件             | git checkout -- filename                    |
|修改  | 移除并删除文件               | git rm [-f] filename                        |
|修改  | 移除但不删除                 | git rm --cached filename                    |
|修改  | 修改名称                     | git mv filename-old filename-new            |
|日志  | 查看提交日志                 | git log                                     |
|日志  | 定制日志格式                 | git log --pretty=format:"%h - %an, %ar : %s"|
|分支  | 新建分支并切换到该分支       | git checkout -b banchname                   |
|分支  | 删除分支                     | git branch -d/-D banchname                  |
|分支  | 当前分支上合并 brnachname    | git merge banchname                         |
|分支  | 取出特性分支在 master 上重演 | git rebase [主分支] [特性分支]              |
|分支  | 从远程拉取最新代码           | git pull origin [远程分支]                  |
|分支  | 推送本地分支到远程           | git push origin localbranch:remotebranch    |
|分支  | 删除指定的远程分支           | git push origin :remotebranch               |
|分支  | 强制 push                    | git push origin +master:master              |
|仓库  | 查看远程仓库                 | git remote [-v]                             |
|仓库  | 添加远程仓库                 | git remote add [shortname] [url]            |
|仓库  | 从远程仓库抓取数据           | git fetch [-p] [remotename]                 |
|仓库  | 移除本地远程仓库             | git remote rm remotename                    |
|标签  | 列出所有标签                 | git tag                                     |
|标签  | 推送 tags 到远程仓库         | git push --tags                             |
|标签  | 打标签                       | git tag -a v1.0 -m 'msg'                    |

## Q&A

### 统计代码

CMD 下直接执行可能失败，可以在右键，Git Bash here 里执行。

#### 提交数统计

```
git log --oneline | wc -l
```

更详细可参考：[Git代码行统计命令集](http://blog.csdn.net/Dwarven/article/details/46550117)

#### 统计代码提交量

```
git log --author="$(git config --get user.name)" --pretty=tformat: --numstat | gawk '{ add += $1 ; subs += $2 ; loc += $1 - $2 } END { printf "added lines: %s removed lines : %s total lines: %s\n",add,subs,loc }'
```

#### 仓库提交都排名前 5

如果看全部，去掉 head 管道即可。

```
git log --pretty='%aN' | sort | uniq -c | sort -k1 -n -r | head -n 5
```

### 基于某次 commit 创建分支

```
git checkout -b branchname 5234ab
```

表示以 commit hash 为 `5234ab` 的代码为基础创建分支。

### 恢复单个文件到指定版本

```
git reset 5234ab wiki.md
```

恢复 wiki.md 文件到 commit hash 为 `5234ab` 时的状态。

### 查看指定 commit 的修改内容

```
git show <commit-hash-id>
```

### 显示指定文件每一行明细

```
git blame <filename>
```

### 查看指定文件的修改历史

```
git log -p <filename>
```

### 查看最近两次的修改内容

```
git log -p -2
```

### stash 的使用

查看 stash 列表：

```
git stash list
```

查看某一次 stash 的改动文件列表（不传参数默认显示最近一次）：

```
git stash show stash@{0}
```
不过 git 的分支功能非常强大，其实建议这类操作都可以通过分支来解决。

### gitk 中文乱码

在~/.gitconfig中添加如下内容

```
[core]
   quotepath = false
[gui]
   encoding = utf-8
[i18n]
   commitencoding = utf-8
[svn]
   pathnameencoding = utf-8
```

更详细可参考 [git 乱码解决方案汇总](http://zengrong.net/post/1249.htm)

### 记住 http(s) 的用户名密码

在有些情况下无法使用 git 协议，比如公司的 git 服务器设置了 IP 白名单，只能在公司内网使用 ssh，那么在外面就只能使用 http(s) 上传下载源码了，但每次都手动输入用户名/密码特别惨，于是乎就记住吧。

设置记住密码（默认 15 分钟）：

```sh
git config --global credential.helper cache
```

自定义记住的时间（如下面是一小时）：

```sh
git config credential.helper 'cache --timeout=3600'
```

长期存储密码：

```sh
git config --global credential.helper store
```
