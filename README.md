# My Fisrt Repository
第一个从零开始创建的 git 仓库
## windows 安装
官网 [下载安装程序](https://git-scm.com/download/win) ，得到 .exe 文件，双击安装一路默认即可；
安装完毕后找到 Git Bash 并打开，显示如下命令行窗口：
 ![Git Bash 命令行窗口](https://uploadfiles.nowcoder.com/images/20210911/616851188_1631368891963/9C4532767A43121E18B4F4ACCD6D7D7A "图片标题") 

输入以下命令行配置用户名与邮箱：
```
git config --global user.name "Your Name"
git config --global user.email "email@example.com"
```
查看配置信息：
```
git config -l
```

## 基本使用
### 一、**创建版本库**
版本库又叫仓库 (repository)，仓库里面的所有文件都可以被 Git 管理，Git 跟踪记录每个文件的创建、修改、删除，并且一定程度上可以恢复历史版本。
1. **创建根目录**：进入想创建仓库的文件目录，**右键 > Git Bash Here**，进入命令行窗口，创建文件夹作为仓库根目录；
2. **进入根目录**： `pwd` 命令可以查看当前目录的绝对路径；
3. **初始化仓库**：初始化目录为 Git 管理仓库（初始为空仓库），`ls -ah` 命令可以查看隐藏的 .git 文件夹，该文件夹用于跟踪管理版本库。
```
mkdir repository_name
cd repository_name
pwd
git init
```
![](README_md_files%5Cimage.png?v=1&type=image)
### 二、添加文件
在仓库中添加文件的三步骤：
1. **创建文件**：在根目录或者子目录下创建文件
2. **将文件添加到仓库**：`git add` + 文件名加扩展名
3. **确认提交**：`git commit -m` + 提交说明，确认修改时最好加上本次操作的说明，方便后续查阅跟新情况
4. **注意**：确认提交可以在添加多文件之后再执行；每次添加文件可以添加多个文件，文件名之间使用 **空格** 隔开
```
git add file_name
git commit -m "Description of the operation"
```

## 三、常用命令行
- **查看仓库状态**：返回仓库中被修改文件的信息（相比上次提交）
```
git status
```
- **对比查看修改内容**
```
git diff file_name
```
