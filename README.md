
# Git 安装配置与常用指令
## windows 安装
官网 [下载安装程序](https://git-scm.com/download/win) ，得到 .exe 文件，双击安装一路默认即可；
安装完毕后找到 Git Bash 并打开，进入命令行窗口：
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

### 二、添加文件
在仓库中添加文件的三步骤：
1. **创建文件**：在根目录或者子目录下创建文件
2. **将文件添加到仓库**：`git add` + 文件名加扩展名
3. **确认提交**：`git commit -m` + 提交说明(可有可无)，确认修改时最好加上本次操作的说明，方便后续查阅跟新情况（提交后返回文件修改信息）
4. **注意**：确认提交可以在添加多文件之后再执行；每次添加文件可以添加多个文件，文件名之间使用 **空格** 隔开
```
git add file_name
git commit -m "Description of the operation"
```

## 常用指令
- **清空命令行与清除命令历史**
```
clear      # 也可以使用快捷键 ctrl+l
history -c # 注释可以写在#之后
```
- **查看文件内容**
```
cat file_name
```
- **查看仓库状态**
```
git status
```
- **对比查看修改内容**
```
git diff file_name
```
- **查看日志**：
 `<--pretty=oneline>` 中尖括号表示可选参数，没有该参数显示跟多信息，有该参数则只显示 commit id 和提交时的说明信息；
  `git log` 查看提交日志；如果版本回退，不能看到新版本的提交日志；
  `git reflog` 查看操作日志；版本恢复可以使用这个命令查看版本号
```
git log <--pretty=oneline>
git reflog <--pretty=oneline>
```
- **回退与恢复版本**：
 **[num]** 为正整数，表示回退多少个版本号，回退一个版本可以简写为 HEAD^；
 也可以通过 commit id 精确回退到指定版本；
 而恢复版本只能通过commit id 实现；
 **--hard** 表示xxxxxxxxxxx
```
git reset --hard HEAD~[num]
git reset --hard HEAD^
git reset --hard commit_id
```



