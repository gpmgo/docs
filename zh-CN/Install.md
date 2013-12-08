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
	   --pkg, -p		only install non-main packages
	   --verbose, -v	show process details
   
### `gopm install`

- 功能：根据当前项目 gopmfile 链接依赖并执行 go install。
- 说明：下载丢失的依赖然后链接并安装它们。
- 示例：`gopm install`。

### `gopm install <import path>`

- 功能：根据指定导入路径 gopmfile 链接依赖并执行 go install。
- 说明：下载丢失的依赖然后链接并安装它们。
- 示例：`gopm install github.com/Unknwon/com`。

## 选项

- `--pkg, -p`：只安装非 main 包。
- `--verbose, -v`：显示详细信息。