
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

## 本地仓库
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

## 远程仓库
### 一、建立本地与远程仓库链接
```
ssh-keygen -t rsa -C "youremail@example.com"
```
- 本地仓库与远程仓库通过 SSH 加密传输，可以在本地创建 SSH key；
- 生成 id_rsa 和 id_rsa.pub 两个文件，分别是密钥和公钥；
- 把公钥添加到 GitHub > Account Settings > SSH keys 中就可以实现本地仓库与远程仓库的双向传输了；
- 不同设备都可以生成密钥和公钥，为远程仓库添加不同的公钥就可以让不同设备同时管理一个远程仓库，推送内容到远程仓库或者从远程仓库克隆到本地仓库

### 二、与远程仓库关联
1. **创建远程仓库**：
 与远程仓库关联之前应当船舰 GitHub 上创建一个空的远程仓库，具体方法是：
 GitHub 右上角 > New repository > 设置仓库名和说明即可
2. **建立远程连接**：
 `account_name` 是用户名
 `repo_name` 是远程仓库名
```
git remote add origin git@github.com:account_name/repo_name.git
```
3. **推送到远程仓库**：
 远程仓库默认名称是 origin，也可以改别名（别名在上一步建立连接时定义），改别名之后别名与 origin 都能用来推送
 第一次推送会有 SSH 警告，输入 yes 回车即可；后续推送可以不加上 -u
```
git push -u origin master
git push origin master
```

