Git is a distributed version control system.
Git is free software.

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
git commit -m "add 3 files"
```


