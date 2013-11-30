gopmfile
====

gopmfile 需放在项目根目录下，名称为 `.gopmfile`。

样例 gopmfile 文件：

	[target]
	path=github.com/gpmgo/gopm
	
	[deps]
	github.com/codegangsta/cli=branch:master

- `target -> path` 指示项目名称或导入路径。
- `deps` 节包含了特殊（非最新）版本的依赖。