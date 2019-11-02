# git 学习笔记



## 2.1git 初始化

git config --global user.name "liuzhijie"

git config --global user.email liu--zhijie@outlook.com

告诉git当前用户的信息



设置一些gie别名，使得命令更加简洁

sudo git config --system alias.br branch

sudo git config --system alias.ci "commit -s"

按照这个设置，git ci 相当于git commit -s, git st 设置为　git -p status

alias.co  ->  checkout



执行git init创建版本仓库

echo "hello." > welcome.txt       创建一个txt，内容为hello

git add welcome.txt    将这个文件添加到版本库

git ci -m "initialized"  提交说明，如果没有-m，会进入编辑器写说明



ｇit config -e --system　　查看设置的文档，之前设置的简洁命令

git config -e --global     查看之前提交的用户信息



git log --pretty=fuller   查看提交历史

--amend 对之前的提交进行补交



git clone demo demo-step-1             备份，会产生一个demo-step-1的文件夹，里面有备份的文件





## 2.2git暂存区



echo "nice to meet you." >> welcome.txt    向这个文档后追加一行

git diff 　显示原始文件和追加后的中间态的文件的比较

git commit -m " append a line "  执行后发现没有提交

git ci查看状态　　（实际为git commit -s)



git add welcome.txt  执行完再执行diff发现没有输出。　diff HEAD能看到差异



git add 把文件添加到暂存区

git commit把所有暂存区的文件提交到当前分支

创建版本库的时候，自动创建了唯一一个master分支，所以git commit 就是往master上提交更改



### 版本回退

git中，HEAD表示当前版本，上一个版本是HEAD^,上上一个是HEAD^^,,往上１００个版本是HEAD~100

使用git reset --hard HEAD^回退到上一个版本

如果还想回到之前的最新版本，可以git reflog查看记录，查到之前commit的id

使用git reset --hard commit_id   就可以回到最新的那个版本





## 3.远程仓库

查看主目录下有没有.ssh文件夹，没有的话创建

ssh-keygen -t rsa -C "youremail.com"



登录github，打开账户设置中的ＳＳＨ　Ｋｅｙｓ

ｔｉｔｌｅ随便写

Ｋey填写.ssh文件夹下面id_rsa_pub的内容



在github上创建一个版本库demo,不要勾选初始化这个仓库



在本地仓库下执行：

git remote add origin git@github.com:NOELliu1/demo.git

继续执行git push -u origin master把内容推送到远程库，-u把本地master分支和远程的master分支关联起来







## 

