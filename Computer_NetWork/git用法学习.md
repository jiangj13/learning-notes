# Git 是什么？
版本控制系统
# 4区域 & 4指令
Git 分为四个重要区域，四个重要指令
工作区 暂存区 本地仓库 远程仓库
add commit push pull

工作区 Working Directory

        ↓ git add

暂存区 Stage / Index

        ↓ git commit

本地仓库 Local Repository

        ↓ git push

远程仓库 GitHub

# 工作区
正在编辑的文档

# 暂存区
git add 可以将文件由工作区放入暂存区

疑问：为什么不直接提交，暂存区的意义在哪？
答案：因为一次需要提交多个文件，同一批次一起提交方便溯源解释。

# 本地仓库
git commit 可以将文件由暂存区提交到本地仓库（只在本地的仓库）

# 远程仓库
git push 可以将本地仓库内文件上传到 GitHub
git pull 则相反，将 GitHub 内文件下载到本地仓库