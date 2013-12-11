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

## 如何编写包版本

有五种可能的包版本组合：

- 空白：表示使用最新版本的依赖进行构建。
- `/path/to/my/project`：绝对或者相对的文件路径，例如：`d:\projects\xorm`。
- `branch:<value>`：固定分支，例如：`branch:master`。
- `tag:<value>`：指定标签，例如：`tag:v0.9.0`。
- `commit:<value>`：某个提交，例如：`commit:6ffffe9`。一般来说只需要 SHA 的前 7 个字母就可以确定一个提交。