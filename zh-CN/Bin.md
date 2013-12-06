bin 命令
====

帮助信息：`gopm bin -h` 或 `gopm bin get`：

	NAME:
	   bin - download and link dependencies and build executable binary
	
	USAGE:
	   command bin [command options] [arguments...]
	
	DESCRIPTION:
	   Command bin downloads and links dependencies according to gopmfile,
	and build executable binary to work directory
	
	gopm bin <import path>@[<tag|commit|branch>:<value>]
	gopm bin <package name>@[<tag|commit|branch>:<value>]
	
	Can only specify one each time, and only works for projects that
	contain main package
	
	OPTIONS:
	   --dir, -d		build binary to given directory(second argument)
	   --update, -u		update pakcage(s) and dependencies if any
	   --verbose, -v	show process details
   
### `gopm bin <import path>@[<tag|commit|branch>:<value>]`

- 功能：下载指定版本的远程包及其依赖并构建可执行文件。
- 说明：无需手动处理源代码即可快速构建二进制文件。
- 示例：
	- 最新版本：`gopm bin github.com/gpmgo/gopm`.
	- 固定分支（branch）：`gopm bin github.com/gpmgo/gopm@branch:master`。
	- 指定标签（tag）：`gopm bin github.com/gpmgo/gopm@tag:tag:v0.1.0`。
	- 某个提交（commit）：`gopm bin github.com/gpmgo/gopm@commit:23ce93a`。
	
#### 使用用例

如果您想要将二进制构建至指定路径，则可以使用 `--dir, -d` 选项来达到目的。例如，我想将 gopm 构建至 `$GOROOT/bin`，则我应该执行 `gopm bin -d github.com/gpmgo/gopm $GOROOT/bin`。

##### 最新版本：`gopm bin github.com/gpmgo/gopm`

该命令下载最新版本的 gopm，并将二进制构建至当前目录。

#### 固定分支：`gopm bin github.com/gpmgo/gopm@branch:master`

该命令下载 gopm 的 master 分支的最新版，并将二进制构建至当前目录。

##### 指定标签：`gopm bin github.com/gpmgo/gopm@tag:tag:v0.1.0`

该命令下载 `tag:v0.1.0` 版本的 gopm，并将二进制构建至当前目录。

##### 某个提交：`gopm bin github.com/gpmgo/gopm@commit:23ce93a`

该命令下载提交 `commit:23ce93a` 时刻的 gopm，并将二进制构建至当前目录。
	
### `gopm bin <package name>@[<tag|commit|branch>:<value>]`

- 功能：下载指定版本的远程包及其依赖并构建可执行文件；但可使用项目名称代替完整的导入路径。
- 说明：该命令为包导入路径的快捷版。
- 示例：
	- 最新版本：`gopm bin gopm`。
	- 固定分支（branch）：`gopm bin gopm@branch:master`。
	- 指定标签（tag）：`gopm bin gopm@tag:v0.1.0`。
	- 某个提交（commit）：`gopm bin gopm@commit:23ce93a`。
	
查看 [知名 Go 项目列表](../pkgname.list) 获取更多信息。

## 选项

- `-dir, -d`：构建可执行文件到指定目录（第二个参数）。
- `--update, -u`：检查更新所有包。
- `--verbose, -v`：显示详细信息。