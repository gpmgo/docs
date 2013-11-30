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
	contains main package
	
	OPTIONS:
	   --dir	build binary to given directory(second argument)
   
### `gopm bin <import path>@[<tag|commit|branch>:<value>]`

- 功能：下载指定版本的远程包及其依赖并构建可执行文件。
- 示例：
	- 最新版本：`gopm bin github.com/beego/beeweb`.
	- 固定分支（branch）：`gopm bin github.com/beego/beeweb@branch:master`。
	- 指定标签（tag）：`gopm bin github.com/beego/beeweb@tag:v1`。
	- 某个提交（commit）：`gopm bin github.com/beego/beeweb@commit:751ff2c`。
	
### `gopm bin <package name>@[<tag|commit|branch>:<value>]`

- 功能：下载指定版本的远程包及其依赖并构建可执行文件；但可使用项目名称代替完整的导入路径。
- 示例：
	- 最新版本：`gopm bin beeweb`。
	- 固定分支（branch）：`gopm bin beeweb@branch:master`。
	- 指定标签（tag）：`gopm bin beeweb@tag:v1`。
	- 某个提交（commit）：`gopm bin beeweb@commit:751ff2c`。
	
查看 [知名 Go 项目列表](../pkgname.list) 获取更多信息。

## 选项

- `-dir`：构建可执行文件到指定目录（第二个参数）.