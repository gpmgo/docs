run 命令
====

帮助信息：`gopm run -h` 或 `gopm help run`：

```
NAME:
   run - link dependencies and go run

USAGE:
   command run [command options] [arguments...]

DESCRIPTION:
   Command run links dependencies according to gopmfile,
and execute 'go run'

gopm run <go run commands>
gopm run -l will recursively find .gopmfile with value localPath
and run the cmd in the .gopmfile, Windows hasn't supported yet,
you need to run the command right at the local_gopath dir.

OPTIONS:
   --tags 		apply build tags
   --local, -l		run command with local gopath context
   --verbose, -v	show process details
```
   
### `gopm run <go run commands>`

- 功能：根据 gopmfile 链接依赖并执行 go run。
- 示例：`gopm run main.go`。

## 选项

- `--tags`：应用构建 tags。
- `--verbose, -v`：显示详细信息。