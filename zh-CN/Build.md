build 命令
====

帮助信息：`gopm build -h` 或 `gopm help build`：

	NAME:
	   build - link dependencies and go build
	
	USAGE:
	   command build [command options] [arguments...]
	
	DESCRIPTION:
	   Command build links dependencies according to gopmfile,
	and execute 'go build'
	
	gopm build <go build commands>
	
	OPTIONS:
	   --verbose, -v	show process details
   
### `gopm build <go build commands>`

- 功能：根据 gopmfile 链接依赖并执行 go build。
- 说明：下载丢失的依赖并链接，然后构建二进制。
- 示例：`gopm build`。

## 选项

- `--verbose, -v`：显示详细信息。