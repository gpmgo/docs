get 命令
====

帮助信息：`gopm get -h` 或 `gopm help get`：

	NAME:
	   get - fetch remote package(s) and dependencies to local repository
	
	USAGE:
	   command get [command options] [arguments...]
	
	DESCRIPTION:
	   Command get fetches a package, and any pakcages that it depents on.
	If the package has a gopmfile, the fetch process will be driven by that.
	
	gopm get
	gopm get <import path>@[<tag|commit|branch>:<value>]
	gopm get <package name>@[<tag|commit|branch>:<value>]
	
	Can specify one or more: gopm get beego@tag:v0.9.0 github.com/beego/bee
	
	If no argument is supplied, then gopmfile must be present
	
	OPTIONS:
	   --gopath	download package(s) to GOPATH
	   --force	force to update pakcage(s) and dependencies
	   --example	download dependencies for example(s)
   
### gopm get

- 功能：根据 gopmfile 拉取远程包及其依赖到本地仓库。
- 示例：`gopm get`。

### gopm get <import path>@[<tag|commit|branch>:<value>]

- 功能：拉取指定版本的远程包及其依赖到本地仓库。
- 示例：
	- 最新版本：`gopm get github.com/lunny/xorm`.
	- 固定分支（branch）：`gopm get github.com/lunny/xorm@branch:master`。
	- 指定标签（tag）：`gopm get github.com/lunny/xorm@tag:v0.2.3`。
	- 某个提交（commit）：`gopm get github.com/lunny/xorm@commit:6ffffe9`。
	
### gopm get <package name>@[<tag|commit|branch>:<value>]

- 功能：拉取指定版本的远程包及其依赖到本地仓库；但可使用项目名称代替完整的导入路径。
- 示例：
	- 最新版本：`gopm get xorm`。
	- 固定分支（branch）：`gopm get xorm@branch:master`。
	- 指定标签（tag）：`gopm get xorm@tag:v0.2.3`。
	- 某个提交（commit）：`gopm get xorm@commit:6ffffe9`。
	
查看 [知名 Go 项目列表](../pkgname.list) 获取更多信息。

## 选项

- `-gopath`：下载包及其依赖至 GOPATH 中。
- `-force`：强制更新包及其依赖。
- `-example`：为示例（example）目录下载依赖。