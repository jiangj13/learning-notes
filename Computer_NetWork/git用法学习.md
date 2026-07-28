# Git 是什么？
版本控制系统
# 4区域 & 4指令
Git 分为四个重要区域，四个重要指令
工作区 暂存区 本地仓库 远程仓库
add commit push pull

```mermaid
flowchart LR
    A[工作区 Working Directory] -- git add --> B[暂存区 Stage]
    B -- git commit --> C[本地仓库 Local Repository]
    C -- git push --> D[远程仓库 GitHub]
```

## 工作区
正在编辑的文档

## 暂存区
git add 可以将文件由工作区放入暂存区

疑问：为什么不直接提交，暂存区的意义在哪？
答案：因为一次需要提交多个文件，同一批次一起提交方便溯源解释。

## 本地仓库
git commit 可以将文件由暂存区提交到本地仓库（只在本地的仓库）

## 远程仓库
git push 可以将本地仓库内文件上传到 GitHub
git pull 则相反，将 GitHub 内文件下载到本地仓库

# 使用方法
## 列顺序 & 加粗 & 表格
- TCP
- UDP

**TCP** **UDP**

|协议|端口|
|-|-|
|HTTP|80|
|HTTPS|443|
|SSH|22|

## 注释方法
一：显示界面看不到
<!-- 此段内容不可见 -->
```
<!-- 此段内容可见 -->
```
## 写代码
例如 使用 `command()`

符号```python
` 
```
适合命令、变量和函数名

或者多行代码块
符号````python
```
````

```python
code row1
code row2
```
## 插入图片 & 流程图
图片插入方法如下:
````markdown
![socket流程图](./images/socket_flow.png)
![图片说明](图片路径)
````

流程图如下:
````
```mermaid
流程图代码
```
````