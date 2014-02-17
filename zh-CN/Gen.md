gen 命令
====

Help information: `gopm gen -h` or `gopm help gen`:

	NAME:
	   gen - generate a gopmfile according current Go project
	
	USAGE:
	   command gen [command options] [arguments...]
	
	DESCRIPTION:
	   Command gen gets dependencies and generates a gopmfile
	
	gopm gen
	
	Make sure you run this command in the root path of a go project.
	
	OPTIONS:
	   --example, -e	check dependencies for example(s)
	   --verbose, -v	show process details
   
### `gopm gen`

- 功能：根据当前 Go 项目生成 gopmfile。
- 说明：获取依赖并写入 gopmfile。
- 示例：`gopm gen`。

#### 使用用例

我现在正在目录 `$GOPATH/src/github.com/beego/beeweb` 下，此时我需要生成一个 gopmfile：

	$ gopm gen
	$ cat .gopmfile
	
输出：

	[deps]
	github.com/astaxie/beego=
	github.com/beego/i18n=
	github.com/Unknwon/com=
	github.com/Unknwon/goconfig=
	github.com/slene/blackfriday=	
	
需要注意的是，该命令只会列出直接依赖包；也就是说它不会记录 beego、i18n、com 包依赖谁，因为这是这些包的作者的责任。

有关如何书写包版本的信息，请阅读 [gopmfile](Gopmfile.md)。


## 选项

- `-example`：为示例（example）目录检查依赖。
- `--verbose, -v`：显示详细信息。
