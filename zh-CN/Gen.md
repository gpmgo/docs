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
	   --example	check dependencies for example(s)
   
### `gopm gen`

- 功能：根据当前 Go 项目生成 gopmfile。
- 示例：`gopm gen`。

## 选项

- `-example`：为示例（example）目录检查依赖。