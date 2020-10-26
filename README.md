# Git 使用说明

## 安装Git
在Windows上安装Git，打开Git Bash，进行初步Global配置：
> $git config --global user.name "Your name" <br/>
> $git config --global user.email "Your email"

## 创建Repository
创建并打开Repository所在的物理路径后，执行git init来创建空的repository。
> git init <br/>

## 工作区、暂存区、本地版本库、远程版本库
- 工作区（Working Directory)
  本地的code change都在工作区
- 暂存区（Temporary Index)
  
- 本地版本库（Local Repository)
  本地路径下有一个.git的folder，即为Stage暂存区，用来存放git repository的相关信息例如：版本信息、指针等。
  
- 远程版本库（Remote Repository)




## Git 命令总结

| Command | Description | Examples |
| -------| ------- | ------- |
| git config | Initialize git configuration such as user.name/user.password. | git config --global user.name xxx |
| git init | Initialize empty repository | git init |
| git add | Add file to temporary index | git add readme.txt |
| git commit | Submit file to local repository | git commit -m "add file" |
| git status | Check current status of local repository | |
| git diff | Check differences between current directory and local repository | git diff readme.txt |
| git log | Check the change logs | git log --pretty=oneline --abbrev |
| git reset | Revert file to previous versions | git reset --hard HEAD^ <br/> `HEAD^ - 上个版本`<br/>`HEAD^^ - 上上个版本`<br/>`HEAD~100 - 上100个版本`<br />`commit-id - 指定版本号` |
| git reflog | Check all the submit logs| |
| 
