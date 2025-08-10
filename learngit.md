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
```
rm test.txt(删除文件) 可通过git status看

从版本库里删除文件:
git rm test.txt
git commit -m "remove test.txt"

删错了：
git checkout -- test.txt(用版本库里的版本替换工作区的版本)
```

## remote repository

### SSH Key
```
看主目录下有无.shh文件 若没有则
ssh-keygen -t rsa -C "youremail@example.com" 添加
后在GitHub 里添加id_rsa.pub 里的密钥
```

### add remote repository
从本地到远程
```
先在github上创建仓库
有本地库时 连接远程库：
git remote add origin(给远程库取名) *git@github.com:759761507/LearnGit.git*(远程库SSH地址)

第一次推送 git push -u origin master
后续提交命令：
git push origin master(把本地master分支最新修改推送至GitHub)


删除本地和远程绑定关系：
git remote -v (查看远程库信息)
git remote rm 名字如origin  解除关系并不是物理删除
```
从远程到本地 克隆clone
```




```