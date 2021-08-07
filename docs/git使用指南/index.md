# Git使用指南


Git常用操作命令

<!--more-->
## 常用概念
> 工作区

本地的工作环境  
> 暂存区

add后会存入到暂存区
> 版本库

commit 后会将暂存区的文件提交到当前分支

## 配置
```shell
git config -e --global
[user]
        name = ***
        email = **@**.com
[alias]
        br = branch
        co = checkout
        ci = commit
        st = status
        lg = log --graph --oneline
```

## 设置ssh方式连接git
```shell
cd ~/.ssh
ssh-keygen -t rsa -C "**@**.com"
ssh-add ~/.ssh/id_rsa_github
# 将id_rsa_github.pub 文件内容复制到Github-SSH keys
# 测试 
ssh -T git@github.com

# windows上可能ssh-agent未启动，需要执行
ssh-add -l -E sha256
eval ssh-agent -s / eval $(ssh-agent)
```

## 设置多个git源ssh连接
```shell
vim ~/.ssh/config
Host gitlab
HostName gitlab.com
User Git
IdentityFile ~/.ssh/id_rsa
Host github.com
HostName github.com
User Git
IdentityFile ~/.ssh/github_rsa
```

## 克隆仓库
```shell
git clone git@github.com:li2251421/li2251421.github.io.git
```

## 新建仓库
```shell
github上New repository
本地新建目录
git init
git add
git commit -m "first commit"
git branch -M master/main
git remote add origin git@github.com:kepreal/test.git
git push -u origin master/main
```

## 新功能开发切分支
```shell
master>git pull
master>git checkout -b feature/test
feature/test>git add
feature/test>git commit -m ""
feature/test>git push -u origin feature/test
```

## 撤销add到暂存区的文件
```shell
git reset HEAD <file>
```

## 撤销修改(恢复到版本库或暂存区)
```shell
git checkout -- file
```
- 文件在暂存区，恢复到暂存区
- 文件不在暂存区，恢复到版本库

## 切功能分支后master有新提交
```shell
git fetch origin
git rebase origin/master
# rebase后只是本地变了，远程的分支结构没变，push时会有冲突
# 单人负责一个分支强制覆盖
git push -u --force origin feature/test
# 多人负责一个分支时需要解决冲突
git rebase -i origin/master
```

## 版本回退
```shell
# ^上一个版本，^^上上一个版本，~2上上个版本
git reset --hard HEAD^
```

## 清除远程不存在的分支
```shell
git remote show origin
git remote prune origin
git branch -d feature/test
```


