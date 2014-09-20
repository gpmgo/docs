get 命令
=======

帮助信息：`gopm get -h` 或 `gopm help get`：

```
NAME:
   get - fetch remote package(s) and dependencies

USAGE:
   command get [command options] [arguments...]

DESCRIPTION:
   Command get fetches a package or packages,
and any pakcage that it or they depend(s) on.
If the package has a gopmfile, the fetch process will be driven by that.

gopm get
gopm get <import path>@[<tag|commit|branch>:<value>]
gopm get <package name>@[<tag|commit|branch>:<value>]

Can specify one or more: gopm get cli@tag:v1.2.0 github.com/Unknwon/macaron

If no version specified and package exists in GOPATH,
it will be skipped, unless user enabled '--remote, -r' option
then all the packages go into gopm local repository.

OPTIONS:
   --download, -d	download given package only
   --update, -u		update pakcage(s) and dependencies if any
   --local, -l		download all packages to local GOPATH
   --gopath, -g		download all pakcages to GOPATH
   --remote, -r		download all pakcages to gopm local repository
   --verbose, -v	show process details
```
   
### `gopm get`

- 功能：根据 gopmfile 拉取远程包及其依赖到本地仓库。
- 说明：如果未传入任何参数，则 gopm 根据在当前目录的项目来进行依赖包的拉取。如果发现 gopmfile 文件，则会应用相关规则。
- 示例：`gopm get`。

#### 使用用例

##### `gopm get`

假设您的当前目录是 gopm（`github.com/gpmgo/gopm`）项目的根目录：

	$ pwd
	
输出：

	$GOPATH/src/github.com/gpmgo/gopm
	
然后在目录下有一个 gopmfile 文件：

	$ cat .gopmfile
	
输出：


	[target]
	path=github.com/gpmgo/gopm
	
	[deps]
	github.com/codegangsta/cli=
	github.com/Unknwon/com=
	github.com/Unknwon/goconfig=
	github.com/aybabtme/color=
	
如果节 `deps` 中的 4 个包不存在于你的 `$GOPATH` 中，则该命令会下载它们（到 gopm 本地仓库 `~/.gopm/repos`）。

假设您需要将他们全部下载到 GOPATH 中，然后做一些修改重新编译 gopm。则您可以使用选项 `--gopath, -g` 来达到目的。

然而，当您希望保持您的 `$GOPATH` 整洁，而将它们全部下载到 gopm 本地仓库。则您可以使用选项 `--remote, -r` 来达到目的。


### `gopm get <import path>@[<tag|commit|branch>:<value>]`

- 功能：拉取指定版本的远程包及其依赖到本地仓库。
- 说明：该命令可接受一个或多个参数附带或不带指定版本。
- 示例：
	- 最新版本：`gopm get github.com/lunny/xorm`.
	- 固定分支（branch）：`gopm get github.com/lunny/xorm@branch:master`。
	- 指定标签（tag）：`gopm get github.com/lunny/xorm@tag:v0.2.3`。
	- 某个提交（commit）：`gopm get github.com/lunny/xorm@commit:6ffffe9`。
	
#### 使用用例

##### 最新版本：`gopm get github.com/lunny/xorm`

该命令下载最新版本的 xorm，并根据 gopmfile 下载它的依赖包。

##### 固定分支：`gopm get github.com/lunny/xorm@branch:master`

该命令下载 xorm 的 master 分支的最新版，并根据 gopmfile 下载它的依赖包。

##### 指定标签：`gopm get github.com/lunny/xorm@tag:v0.2.3`

该命令下载 `tag:v0.2.3` 版本的 xorm，并根据 gopmfile 下载它的依赖包。

##### 某个提交：`gopm get github.com/lunny/xorm@commit:6ffffe9`

该命令下载提交 `commit:6ffffe9` 时刻的 xorm，并根据 gopmfile 下载它的依赖包。

### `gopm get <package name>@[<tag|commit|branch>:<value>]`

- 功能：拉取指定版本的远程包及其依赖到本地仓库；但可使用项目名称代替完整的导入路径。
- 说明：该命令为包导入路径的快捷版。
- 示例：
	- 最新版本：`gopm get xorm`。
	- 固定分支（branch）：`gopm get xorm@branch:master`。
	- 指定标签（tag）：`gopm get xorm@tag:v0.2.3`。
	- 某个提交（commit）：`gopm get xorm@commit:6ffffe9`。
	
查看 [知名 Go 项目列表](../pkgname.list) 获取更多信息。

## 选项

- `--download, -d`：仅下载当前指定的包。
- `--update, -u`：检查更新所有包。
- `--gopath, -g	`：下载所有包至 GOPATH 中。
- `--remote, -r`：将所有包下载至 gopm 本地仓库。
- `--verbose, -v`：显示详细信息。