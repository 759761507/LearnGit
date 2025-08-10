Git is a distributed version control system.
Git is free software distributed under the GPL.
Git has a mutable index called stage.
Git tracks changes.

## install git in Linux
```
git
sudo apt-get install git
git config --global user.name "Your Name"
git config --global user.email "email@example.com"
```

## create repository
```
创建目录 mkdir name
cd name

git init(Initialized empty Git repository in /Users/michael/name/.git/)

新创建的文件要在name目录下或子目录
git add readme.txt
git commit -m "wrote a readme file" (-m后面是本次提交的说明)
```

为什么需要add和commit两步？
```
git add file1.txt
git add file2.txt file3.txt
git commit -m "add 3 files"(add 可添加多次)
```

## change file content
### modify
```
git status(看工作区的状态)

git diff readme.txt(查看修改内容)
或git diff HEAD -- readme.txt

git add readme.txt
git status
git commit -m "add ..."
```
### return to previous version
```
commit 保存版本

git log (查看历史记录) 简介版本： git log --pretty=online

git reset --hard HEAD^(删除了原来版本记录)
(HEAD是当前版本 HEAD^ 上一版本 HEAD^^ 上上一版本 HEAD~100上100版本)
(--hard会回退到上个版本的已提交状态)

git reset --hard 1094a版本号(可找回版本)或 git reflog (查看命令历史)
```
### concept
工作区 版本库=暂存区stage+分支master   add添加到暂存区 commit提交暂存区文件

### cancel change
```
1. git checkout -- readme.txt(文件还没添加到缓存区 直接丢弃工作区修改)

2. git reset HARD readme.txt(把暂存区的修改撤销掉 再步骤1 ) reset既可以回退版本 也可以一把暂存区的修改回退到工作区
```

### remove file

