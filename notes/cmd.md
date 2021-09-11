
# 本地仓库操作指令
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
- **暂存区撤回**：`git add` 是将文件添加到暂存区，但没有提交到版本库中，就可以从暂存区撤回；指定文件名就只撤回指定文件，否则撤回暂存区中的所有文件
```
git reset HEAD <file_name>
```
- **文件替换**：用版本库中的文件替换工作区的文件；错误删除或者错误修改时可以通过这个方法替换指定文件而无需回退版本
```
git checkout -- file_name
```
- **删除文件**：
 `rm file` 在工作区删除文件
 `git rm file` 在版本库删除文件，删除后提交修改
```
rm file
git rm file
git commit -m "Delete file"
```

# 远程仓库操作指令
- **查看远程库信息**：
```
git remote -v
```
- **解绑本地与远程库关系**：
```
git remote rm origin
``
