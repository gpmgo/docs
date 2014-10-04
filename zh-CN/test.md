test 命令
========

帮助信息：`gopm test -h` 或 `gopm test run`：

```
NAME:
   test - link dependencies and go test

USAGE:
   command test [command options] [arguments...]

DESCRIPTION:
   Command test links dependencies according to gopmfile,
and execute 'go test'

gopm test <go test commands>

OPTIONS:
   --tags 		apply build tags
   --verbose, -v	show process details
```
   
### `gopm test <go test commands>`

- 功能：根据 gopmfile 链接依赖并执行 go test。
- 示例：`gopm test`。

## 选项

- `--tags`：应用构建 tags。
- `--verbose, -v`：显示详细信息。