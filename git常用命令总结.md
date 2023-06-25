# 分支 
git branch -vv  显示本地分支 和远程分支之间的关系 

 git branch -d [BranchName]  删除本地分支

git push [远程地址]  [本地分支]:[远程分支]  eg： git push origin master:feature/p3 

git diff [本地分支]  [远程服务器]/[远程分支]  eg  git diff  master origin/feature/p3  比较本地分支和远程分支的区别，push之前最好比较检查 

git branch --set-upstream-to=origin/[branch] master  设置本地分支master跟踪origin/[branch]远程分支

git branch --set-upstream 本地新建分支名 origin/远程分支名

git checkout -b 本地分支名x origin/远程分支名x        拉取远程分支并创建本地分支
 
git checkout [-f] [本地分支]  切换本地分支, -f 强制切换，忽略unmerge file 

git remote update origin --prune     更新远程分支列表

git remote update origin -p    更新远程分支列表

git branch -m [原分支名] 新分支名 

git branch 分支名   新建分支


# 强制覆盖本地代码：
 git fetch --all

 git reset --hard origin/master 

 git pull

# 分支合并比较
 git diff --stat-width=200 familyStructure origin/feature/p4  有差异的文件集合

 git merge 

# 合并分支特定目录 
 git cherry-pick     
20c2f506d789bb9f041050dc2c1e954fa3fb6910 
2633961a16b0dda7b767b9264662223a2874dfa9 

  git cherry-pick  -n    手动提交 
 20c2f506d789bb9f041050dc2c1e954fa3fb6910 
 2633961a16b0dda7b767b9264662223a2874dfa9

 detail info ：  https://blog.csdn.net/jxianxu/article/details/79240158  
 
 # 获取历史修改记录 
 git log      获取历史所有的修改记录 
 git log --pretty=oneline      单行显示历史所有记录 
 git log <file-path>         指定文件的历史修改 
 
 #  git show 查看提交的详情  
 
  git show               查看最新的commit
 
  git show commitId       查看指定commit hashID的所有修改 
 
  git show commitId fileName   查看某次commit中具体某个文件的修改

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

如果对于已修改的所有内容，我们都不想要了，想回到最干净的上个提交版本的状态。那么，3个命令就可以搞定一切： 

   git reset

   git checkout .

   git clean -fdx

# git revert 
git revert (--continue | --skip | --abort | --quit).

# git merge 
--no-commit

--no-commit 参数使得合并后，为了防止合并失败并不自动提交，能够给使用者一个机会在提交前审视和修改合并结果。（这个使用后不会合并为一次commit）

# 将本地文件夹初始化为git仓库，并上传到对应的github远程仓库中
git init

git add .

git commit -m "message info"

git remote add origin {shh or http address}

git remote -v

git push -u origin master

# 将多个commit 合并为一个
git log 查看要合并的commit. 记住最早的commit号。

git reset commit_number . 回退到此commit号。 ...

git add . 将回退的的内容再次添加到暂存区

git commit -m "comment" . 再次提交。

git log 。
