git init //初始化版本库
----------------------------------------------------------------------------   
                    //直接修改文件即修改工作区
git add <filename>  //把工作区文件添加到暂存区
git commit -m <"说明"> //把暂存区文件添加到master版本库
-----------------------------------------------------------------------------
git status//时刻掌握仓库当前的状态，上面的命令告诉我们，readme.txt被修改过了，但还没有准备提交的修改。
git diff//虽然Git告诉我们readme.txt被修改了，但如果能看看具体修改了什么内容，自然是很好的。
         比如你休假两周从国外回来，第一天上班时，已经记不清上次怎么修改的readme.txt，
         所以，需要用git diff这个命令
git log (--pretty=oneline)//差看有几个版本被提交到Git仓库里
git reflog   //查看命令历史，以便确定要回到未来的哪个版本
-------------------------------------------------------------------------------
git reset --hard HEAD^ //有几个^表示前几个版本，HEAD为当前版本，或 HEAD~88为前88个版本，
                       回到哪个版本，HEAD指针指向哪个版本  
或者git reset --hard <版本号>

git checkout -- <fliename>//用版本库里的版本替换工作区的版本，
                           无论工作区是修改还是删除，都可以“一键还原”
git reset HEAD <filename>//可以把暂存区的修改撤销掉（unstage），重新放回工作区

git rm <filename>  //删除版本库的文件

-----------------------------------------------------------------------------------
//github的使用
ssh-keygen -t rsa -C “807564945@qq.com” //github的ssh创建

git remote add origin git@github.com:Nzzz/learngit.git  //关联远程库

git push -u origin master //把本地库的内容推送到远程，即把当前分支master推送到远程
                             第一次推送master分支时，加上了-u参数

git clone git@github.com:Nzzz/learngit.git //把远程库克隆到本地库

------------------------------------------------------------------------------------
//分支管理
查看分支：git branch

创建分支：git branch <name>

切换分支：git checkout <name>

创建+切换分支：git checkout -b <name>

合并某分支到当前分支：git merge <name>

删除分支：git branch -d <name>