# git 自定义仓库



#### 服务器端

1. 切换到 git 用户（如果有）
2. 进入 git 目录（如果有），创建 hello.git 文件夹
3. 切换到 hello.git 目录，并初始化该库  **git --bare init**





#### 客户端

**首先需要安装git**

1. 进入项目，同名hello 文件夹，

2. 初始化文件夹  **git init** 

3. 添加所有文件到本地索引  **git add -A**

4. 提交所有文件 **git commit -a -m "init commit"**

5. git remote add 【主机名】 【地址】

   例如：**git remote add origin  git@git.gupiaoxianji.com:/data/git/coinbull_erp.git** 

6. 将本地库push到远程库  **git push origin master**