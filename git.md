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