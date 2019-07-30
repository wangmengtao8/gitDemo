创建版本库
	初始化一个Git仓库，使用 git init 命令。
	添加文件到Git仓库，分两步：
		1、使用命令 git add <file>,注意，可反复多次使用，添加多个文件；
		2、使用命令 git commit -m <message>,完成。
		
时光机穿梭
	版本回退
		1、使用命令 git log 查看历史版本；
		2、使用命令 git reset --hard HEAD^ 回退到上一个版本，
		   使用命令 git reset --hard 版本号 回退到任何版本；
		3、命用命令 git reflog 可以查看所有操作记录。
		现在总结一下：
		HEAD指向的版本就是当前版本，因此，Git允许我们在版本的历史之间穿梭，使用命令git reset --hard commit_id。
		穿梭前，用git log可以查看提交历史，以便确定要回退到哪个版本。
		要重返未来，用git reflog查看命令历史，以便确定要回到未来的哪个版本。
	工作区和暂存区
		1、使用命令 git status 可以查看工作区状态；
		2、使用命令 git add <file> 可以工作区里新增的和修改的文件存入到暂存区；
		3、使用命令 git commit -m <message> 把暂存区里的所有文件存入到master版本中。
	管理修改
		使用命令 git diff HEAD -- readme.txt 可以查看工作区和版本库里面最新版本的区别
	撤销修改
		命令git checkout -- readme.txt意思就是，把readme.txt文件在工作区的修改全部撤销，这里有两种情况：
		一种是readme.txt自修改后还没有被放到暂存区，现在，撤销修改就回到和版本库一模一样的状态；
		一种是readme.txt已经添加到暂存区后，又作了修改，现在，撤销修改就回到添加到暂存区后的状态。
		总之，就是让这个文件回到最近一次git commit或git add时的状态。
	删除文件
		1.如果你用的rm删除文件，那就相当于只删除了工作区的文件，如果想要恢复，直接用git checkout -- <file>就可以 
		2.如果你用的是git rm删除文件，那就相当于不仅删除了文件，而且还添加到了暂存区，需要先git reset HEAD <file>，然后再git checkout -- <file> 
		3.如果你想彻底把版本库的删除掉，先git rm，再git commit 就ok了
		
远程仓库
		生成SSH密钥命令 ssh-keygen -t rsa -C "wangmengtao8@139.com"
	添加远程库
		关联远程库命令 git remote add origin git@github.com:michaelliao/learngit.git
		第一次上传到远程库命令 git push -u origin master，上传到远程库命令 git push origin master；
	从远程库克隆
		克隆远程库命令 git clone git@github.com:michaelliao/learngit.git
		
分支管理
	创建与合并分支
		创建分支命令 git checkout -b dev,创建了分支dev,git checkout 命令加上-b参数表示创建并切换
		查看分支命令 git branch
	解决冲突
	分支管理策略
	Bug分支
	Feature分支
	多人协作
	Rebase
	
		
		
		
