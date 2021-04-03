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

### Github SSH指南：

##### https://docs.github.com/en/github/authenticating-to-github/generating-a-new-ssh-key-and-adding-it-to-the-ssh-agent#generating-a-new-ssh-key

##### https://docs.github.com/en/github/authenticating-to-github/adding-a-new-ssh-key-to-your-github-account

##### 解决SSH登录时出现(Warning: Permanently added the RSA host key for IP address '13.229.188.59' to the list of known hosts.)告警问题
```
创建~/.ssh/config文件，内容如下：
UserKnownHostsFile ~/.ssh/known_hosts
```



##### 1. 按照GitHub官方指导生成本机的SSH-key  并添加到对应的项目中
##### 2. git 远程提交命令
```
git remote add <name> <远程仓库地址>       关联远程仓库
git remote rm <name>                     删除远程仓库链接，不会删除远程仓库
git remote rename <old_name> <new_name>  修改仓库名
git push -u origin master                将本地master推送到远程仓库  git push <远程主机名> <本地分支名>:<远程分支名>
                                         --allow-unrelated-histories 如果远程仓库不是新建的可能会提交失败，合并远程仓库和本地仓库加上 
                                         -u                          首次推送 ，后续执行推送不需要
                                         --force                     强制推送
git push <远程主机名> --delete master      删除远程仓库上的master分支

git fetch    通常通过互联网（使用 http:// 或 git:// 协议) 与远程仓库通信,获取工作区没有的数据，它可能已经将进行这一操作所需的所有数据都下载了下来，但是并没有修改你本地的文件。
             所以，你可以将 git fetch 的理解为单纯的下载操作。
git pull <远程主机名> <远程分支名>:<本地分支名>     从远程仓库更新到本地仓库,远程载入合并本地分支
                                               相当于 git fetch + git merge <远程主机名/别名>/<本地分支名>
```
