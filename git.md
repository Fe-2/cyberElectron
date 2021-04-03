# git常用命令：

```
git config --global user.name ‘yzr’                    配置全局用户名
git config --global user.email ‘yzr.main@outlook.com’  配置全局用户邮箱
git config --list                                      输出配置信息

git init    在当前目录初始化git
git status  查看当前文件状态
git log     输出提交记录日志
git log --oneline --graph   图形化提交记录
git reflog  查看引用版本号

git add  <file>/ .    将文件提交到暂存区    . 表示添加所有变化文件 或者 -A  --all
git commit -m <file>  将文件提交到版本区 -a 表示添加所有变化文件

git diff           比较工作区和暂存区的文件差异
git diff --cached  比较暂存区和版本区的文件差异
git diff master    比较工具去和版本区的文件差异, master代表主分支，比较不同分支替换分支名称即可

git reset HEAD <file>       暂存区和版本区保持一致
git reset --hard <version>  恢复版本区指定版本到工作区
git checkout <file>         暂存区（如果暂存区无内容，将使用版本区）内容覆盖工作区内容
git restore <file>     丢弃工具区改动（回滚） --staged   取消暂存区变化
git rm <file> --cached 删除暂存区文件
git rm <file>          同时删除工作区和版本区文件
git commit -a -m <msg> = git add . + git commit -m 'msg' 一次性将工作区提交到暂存区，再到版本区（第一次提交不可用，第一次提交必须先git add .）

git branch             查看分支
git branch <name>      创建分支
git branch -d <name>   删除分支
git checkout <name>    切换分支
git checkout -b <name> 创建分支并切换  

git merge <name>   合并分支
```
# GitHub远程提交

### Github SSH指南：https://docs.github.com/en/github/authenticating-to-github/generating-a-new-ssh-key-and-adding-it-to-the-ssh-agent#generating-a-new-ssh-key