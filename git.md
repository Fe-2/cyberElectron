# git常用命令：

```
git config --global user.name ‘yzr’  配置全局用户名
git config --global user.email ‘yzr.main@outlook.com’  配置全局用户邮箱
git config --list  输出配置信息

git init   在当前目录初始化git
git status  查看当前文件状态
git log 输出提交记录日志

git add  <file>/ .  将文件提交到暂存区    . 表示添加所有变化文件
git commit -m <file>/ -a  将文件提交到版本区 -a 表示添加所有变化文件

git diff           比较工作区和暂存区的文件差异
git diff --cached  比较暂存区和版本区的文件差异
git diff master    比较工具去和版本区的文件差异, master代表主分支，比较不同分支替换分支名称即可

git reset HEAD <file>  暂存区和版本区保持一致
git checkout <file>    暂存区（如果暂存区无内容，将使用版本区）内容覆盖工作区内容

git 
```
# GitHub远程提交