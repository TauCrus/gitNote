### ﻿基本操作

**git add** 【文件名】 
--请文件添加到暂存区,可多次添加

**git commit -m  "备注"** 
--提交暂存区文件

**git status** 	
--查看仓库当前状态

**git diff**
--查看文件差异

**git log**
--查看提交日志

**git reset --hard HEAD^ / commit_id**
--回退版本，HEAD表示最新版，HEAD^代表上一个版本. 
--git reset 既可以回退版本，也可以把暂存区的修改回退到工作区

**git reflog**
--查看命令历史

**git checkout --  【文件名】**
--撤销修改，如果没有 -- 就会变成切换到另一个分支的指令

**git rm 【文件名】**
--删除文件，删除完需要提交

------

#### 远程仓库

**git clone git@server-name:path/repo-name.git**
--克隆仓库，注意：除了默认的git协议，还可以使用https协议等其他协议

**git remote add origin git@server-name:path/repo-name.git**
--管理远程库

**git push -u origin master**
--第一次提交的时候推送的时候加上，以后可以省略成git push origin master
--**git push是<本地分支>:<远程分支>**



**git fetch <主机名> <远程分支名>:<本地分支名>**
--相当于是从远程获取最新版本到本地，不会自动合并。

**git pull <主机名> <远程分支名>:<本地分支名>**
--获取远程仓库的最新版本并merge到本地，相当于git fetch 和 git merge
--**git pull是<远程分支>:<本地分支>**



------

####  分支管理

**git branch**
--查看分支
-- git branch -a 查看远程分支

**git branch 【分支名】**
--创建分支

**git checkout 【分支名】**
--切换分支

**git checkout -b 【分支名】**
--创建并切换分支

**git merge 【分支名】**
--合并某分支到当前分支

**git branch -d 【分支名】**
--删除分支

**git log --graph --pretty=oneline --abbrev-commit**
--查看分支图

------



#### 临时存储

**git stash**
--储存

**git stash list**
--查看储存的stash

**git stash pop**
--恢复储存同时把stash的内容删除，相当于git stash apply 恢复储存 加 git stash drop删除

------



#### 标签管理

**git tag  【标签】**
--创建一个标签

**git tag -a  【标签】  -m "description"**
--创建指定标签信息

**git tag -s 【标签】 -m "description"**
--创建PGP签名的标签

**git tag**
--查看所有标签

**git show 【标签】**
--查看指定标签信息

**git push origin 【标签】**
--推送一个本地标签

**git push origin --tags**
--可以推送所有本地标签

**git tag -d 【标签】**
--可以删除一个本地标签

**git push origin :refs/tags/【标签】**
--可以删除一个远程标签

------

--当需要忽略某些文件时，需要编写.gitignore



#### Windows 下安装git

1、下载安装程序，默认选项安装
2、打开 Git Bash
3、输入如下内容
git config --global user.name "Your Name"
git config --global user.email "email@example.com"