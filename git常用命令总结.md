# 分支 
git branch -vv  显示本地分支 和远程分支之间的关系 

 git branch -d [BranchName]  删除本地分支

git push [远程地址]  [本地分支]:[远程分支]  eg： git push origin master:feature/p3 

git diff [本地分支]  [远程服务器]/[远程分支]  eg  git diff  master origin/feature/p3  比较本地分支和远程分支的区别，push之前最好比较检查 

git branch --set-upstream-to=origin/[branch] master  设置本地分支master跟踪origin/[branch]远程分支

git branch --set-upstream 本地新建分支名 origin/远程分支名
 
git checkout [-f] [本地分支]  切换本地分支, -f 强制切换，忽略unmerge file 

# 强制覆盖本地代码：
$ git fetch --all

$ git reset --hard origin/master 

$ git pull

# 删除untrack files

 删除当前目录下untrack文件，不包括文件夹和.gitignore中指定的文件和文件夹
 
 git clean -f

 删除当前目录下untrack文件和文件夹， 不包括.gitignore中指定的文件和文件夹
 
  git clean -df

删除当期目录下的所有untrack的文件和文件夹

git clean -xdf

显示会被删除的文件

git clean -nxfd

git clean -nf

git clean -nfd
