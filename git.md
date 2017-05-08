## git 总结
### 初始化 git 仓库

1. git init
2. 用 ls -ah, 可以查看文件夹里所有隐藏文件

### 查看文件状态
1. git status
2. git diff [文件名]

### 提交文件
1. git add [文件名]
2. git commit -m "描述信息"

### 版本回退
1. git log 查看版本信息
2. 版本回退的几种方式 \
    2.1 回退到上个版本 git reset --hard HEAD^ \
    2.2 回退到上上个版本 git reset --hard HEAD^^ \
    2.3 回退到指定版本 git reset --hard HEAD~N \
    2.3 回退到制定版本号 git reset --hard [版本号] 
    2.4 回退到指定提交记录号 git reflog 查看提交记录 
    2.5 回退到指定提交记录号 git reset --hard [提交记录号] 
3. git 内部有个指向当前版本的 HEAD 指针, 回退的时候仅仅是把 HEAD 指针指向指定的版本, 然后更新工作区文件

### 工作区和暂存区
1. 工作区就是当前文件放的目录
2. 版本库 .git \
    2.1 .git 里放了很多东西, 最重要的是称为 stage 的暂存区 \
    2.2 还有 git 为我们自动创建的第一个分支 master, 以及指向 master 的一个指针 HEAD
    ![](./1.png) 
3. 把文件往 git 版本库里添加的时候是分两步执行的 \
    3.1 用 git add 把文件添加进去, 实际上就是把文件修改添加到暂存区\
    3.2 用 git commit 提交更改, 实际上就是把暂存区所有内容提交到当前分支 \

### 管理修改
1. git 不是追踪文件, 而是追踪修改
2. 提交修改
    2.1 每次修改，如果不add到暂存区，那就不会加入到commit中
3. 撤销修改
    3.1 撤销工作区修改, git checkout -- [文件名], 让这个文件回到最近一次 git commit 或 git add 时的状态
    3.2 撤销暂存区修改, git reset HEAD [文件名], git reset命令既可以回退版本，也可以把暂存区的修改回退到工作区。当我们用HEAD时，表示最新的版本
4. git rm [文件名], 用于删除版本库中的文件, 一旦删除无法用 git checkout -- [文件名] 命令恢复, 只能用版本回退恢复

### 关联远程仓库
1. 关联远程仓库: git remote add origin git@server-name:path/repo-name.git
2. 把远程仓库拉取下来: git pull origin master --allow-unrelated-histories
3. 把本地仓库 push 到远程仓库 git push -u orgin master

### 从远程仓库克隆
1. 从远程仓库 clone: git clone git@github.com:[用户名]/[repo名].git
2. git 可以使用多种协议, 如 https, 但是 https 速度慢, 而且每次必须输入口令, 在有些公司只有 http 的端口, 就不能用了

### 分支管理




