- 初始化仓库
```
git init
```
会生成.git文件

- 查看状态
```
git status
```

- 添加到暂存区
	将某个文件的改动添加到暂存区
	```
	git add 文件名
	```
	将当前目录所有文件的改动添加到暂存区
	```
	git add .
	```

-  将暂存区内容提交至版本库并添加信息描述
```
git commit -m '信息描述'
```

- 查看提交记录
```
git log
```

	查看某个文件的commit记录
```
	git log 文件名
```

	查看某个人提交得记录
```
	git log --author="作者name"
```
	摁q可以退出这个查看状态

- 有文件被落下，补充提交到上一次得提交记录中
```
git commit --amend --no-edit
```

- 不想让git追踪文件
增加一个.gitignore，在里面写入不想要最终得文件名就好

- 设置git全局姓名与邮箱
```
git config --global user.name "JunL"
git config --global user.email "JunL@163.com"
```
   将global改为local时，设置只对当前目录有效
   
- 克隆别人的仓库
要克隆别人的 Git 仓库，请使用以下命令：
```
git clone <repository-url>
```

- 将本地仓库推送到远程仓库需要使用git push命令，格式为：
	
	```
	git push <remote> <branch>
	```
	
	其中，`<remote>`是指远程仓库的名称，例如origin；`<branch>`是指要推送的分支名称，例如master。
	
	如果第一次推送某个分支，需要指定该分支的上游分支（即要把哪个分支推送到远程仓库对应的分支），并且在push命令中加上`-u`参数，例如：
	
	```
	git push -u origin master
	```
	
	这样就会把本地的master分支推送到远程的origin仓库，并把origin/master作为本地master分支的上游分支。以后再执行git push命令时，就可以省略参数了，直接用以下命令：
	
```
	git push
```

- 可以使用以下命令将远程仓库最新改动拉取到本地：
	
	```
	git pull
	```
	
	这将自动获取最新的代码，并将其合并到您当前所在的分支中。如果您需要指定特定的远程仓库和分支，请使用以下命令：
	
	```
	git pull <远程仓库名称> <分支名称>
	```
	
	例如，要将名为 origin 的远程仓库的 master 分支更新到本地，可以运行以下命令：
	
	```
	git pull origin master
	```

- 回退版本
	```
	git revert <commit-hash>
	```
	
	这将创建一个新的提交，该提交将撤销指定的提交。
	
	如果您真的需要回退远程分支到较早的提交，可以使用以下命令：
	
	```
	git push -f <remote-name> <commit-hash>:<branch-name>
	```
	
	其中 `<commit-hash>` 是您要回退到的提交的哈希值，`<branch-name>` 是要更新的远程分支名称，`-f` 标志表示强制推送，这将使Git忽略任何可能与您的更改冲突的现有提交。请注意，这将破坏所有基于旧提交构建的任何部署或集成环境。

- 查看之前commit的记录的哈希值
```
git reflog
```

此命令将列出每个HEAD引用的历史记录条目，其中每个条目都有一个唯一的哈希值和一个对应的操作（如提交、重置、合并等）。