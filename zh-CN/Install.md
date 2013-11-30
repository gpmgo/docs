install 命令
====

帮助信息：`gopm install -h` 或 `gopm help install`：

	NAME:
	   install - link dependencies and go install
	
	USAGE:
	   command install [command options] [arguments...]
	
	DESCRIPTION:
	   Command install links dependencies according to gopmfile,
	and execute 'go install'
	
	gopm install
	gopm install <import path>
	
	If no argument is supplied, then gopmfile must be present
	
	OPTIONS:
	   --verbose	show process details
   
### `gopm install`

- 功能：根据当前项目 gopmfile 链接依赖并执行 go install。
- 示例：`gopm install`。

### `gopm install <import path>`

- 功能：根据指定导入路径 gopmfile 链接依赖并执行 go install。
- 示例：`gopm install github.com/Unknwon/com`。

## 选项

- `-verbose`：打印过程信息。