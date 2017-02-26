##git笔记

> 创建一个.gitignore文件可以忽略不需要add的配置文件。

####git基本命令
- `$git init` 初始化git项目
- `$git clone [url]` 克隆一个git项目
- `$git status`查看当前状态
- `$git diff`工作区与暂存区对比
- `$git diff master`工作区与版本区对比
- `$git diff --cached`暂存区与版本区对比

####git提交流程
- 工作区
	- `$git add .`添加到暂存区（注意：不能直接提交到版本区）
	- `$git reset HEAD [fileName]` 撤销以上add命令
- 暂存区
	- `$git commit -m "desc"` 提交到版本区
	- `$git checkout [fileName]`暂存区回滚到工作区
- 版本区
	- 创建源
		- `$git remote add [orgin | name] [url]` 创建一个源
		- `$git remote show`查看所有源
		- `$git remote show [orgin]`查看指定源信息
		- `$git remote rm [orgin]`删除一个源
	- `$git push -u [orgin | name] [master]` 推到github上
	- `$git pull [orgin]`在orgin源中，下拉最新项目
	- `$git reset --hard [版本号]`回滚到指定版本
	- `$git log && $git reflog` 查看提交的版本 和 所有版本


####git分支管理
- 主分支，通过主分支建立一个分支，当代码确认无误合并到主分支。
- 要将文件提交到当前分支才会归当前分支

1. 创建一个分支
	- `$git branch [分支名]` 会在主分支下克隆一份 **注意：**新初始化的git项目必须提交到版本区，才可以创建新的分支
2. 查看所有分支
	- `$git branch`
3. 切换分支
	- `$git checkout [分支名]`
4. 删除分支
	- `$git branch -D [分支名]`
5. 合并分支
	- `$git merge [分支名]` 需要切换到主分支合并，任意分支都可以作为主分支合并。
6. 创建分支并切换到该分支中
	- `$git checkout -b [分支名]`


>解决冲突问题 1. 修改文件，保留正确的代码  2.回到命令工具重新提交
