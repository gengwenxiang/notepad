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
git log --oneline
git diff  比较修改的不同

#### 2. 查看当前配置
git config --list

#### 3. 把当前文件夹变成Git仓库（本地初始化）
git init

#### 4. 克隆远程仓库到本地
git clone https://github.com/用户名/仓库名.git
