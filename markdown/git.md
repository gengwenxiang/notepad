#### 基础
git init  初始化一个仓库  
git clone [git-url]  克隆一个已存在的仓库

#### 配置
git config --global user.name "your name"  设置用户名  
git config --global user.email "your email"  设置邮箱地址  
git config --global --list  查看当前配置

#### 暂存/提交
git add .  暂存所有修改   
git add [file_path]  暂存一个特定的文件  
git commit -m "commit messages"  提交暂存的修改

#### 查看修改
git status  查看状态  
git log  查看日志  
git log --oneline  精简查看日志    
git diff  比较修改的不同

#### 管理分支
git branch  列出所有分支  
git branch  [branch-name]  创建一个新的分支  
git checkout [branch-name]  切换到一个指定分支  
git checkout -b [branch-name]  创建并切换到一个新分支  
git branch -d [branch-name]  删除一个指定分支

#### 远程仓库
git remote add [git-url]  添加一个远程仓库    
git remote -v  列出所有远程仓库  
git pull [remote-name] [branch-name]  拉起一个远程分支到本地  
git branch [remote-name] [branch-name]  push本地修改到一个远程仓库

#### 取消修改
git reset --herd HEAD~1  撤销最近的提交  
git reset  取消暂存的修改  
git checkout --[file-path]  丢弃工作目录中的修改  

#### 合并
git merge [branch-name]  合并指定的分支到当前分支  
git rebase [branch-name]  把当前分支的修改基于指定分支重新应用（变基）  
git tag [tag-name]  在当前提交上创建一个tag标签