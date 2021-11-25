# RemoteR
尝试本地仓库拉取远程仓库+本地仓库上传

## 本地创建并提交至本地仓库

在本地创建文件【状态：Untracked files】
touch <filename>

将文件加入暂存区域
git add <filename>  / git add .

提交到本地仓库
git commit <filename>

## 本地仓库上传文件到远程仓库

先创建连接
git remote add origin https://...      [origin 是远程仓库的名字 代指https://github...这个远程仓库]
或者
当本地克隆远程仓库时，也会创建连接  git clone https://...

上传
git push -u origin master              [origin 是远程仓库的名字，master是里面的分支名，第一次上传需要 -u,其余都不需要]

## 本地仓库拉取远程仓库

git fetch origin branch1               [branch1 是远程仓库的分支名]
或
git pull origin branch1   

## 切换分支

创建分支
git branch <branchname>                 [branchname 分支名]

切换分支
git checkout <branchname>

一步创建切换分支
git checkout -b <branchname>

## 开发中会用到的命令流程

一、开发分支（dev）上的代码达到上线的标准后，要合并到 master 分支
git checkout dev
git pull
git checkout master
git merge dev
git push -u origin master

二、当master代码改动了，需要更新开发分支（dev）上的代码
git checkout master 
git pull 
git checkout dev
git merge master 
git push -u origin dev
