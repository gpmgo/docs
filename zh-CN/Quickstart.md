快速入门
=======

在本小节中，我们将会演示一个安装两种不同版本的 beego 并打印版本信息的简单示例。

## 准备工作

您不需要将这个项目置于任何 `$GOPATH` 下，所以我们就将它放在  `~/demo` 中：

	$ mkdir ~/demo
	$ cd ~/demo
	
然后，创建 `main.go` 文件:

	$ touch main.go
	
复制以下代码并粘贴到文件中：

```go
package main

import (
	"github.com/astaxie/beego"
)

func main() {
	println("Beego version:", beego.VERSION)
}
```

很好！

## gopmfile

这个文件包含 gopm 所需要的所有信息，我们现在就来看看可以在这个示例中对它做什么。

首先，您需要在项目目录中创建 `.gopmfile` 文件：

	$ touch .gopmfile
	
不错，接着把以下内容复制到文件中：

	[target]
	path = demo
	
键 `path` 指示了您的项目名称。

**注意事项** 如果您的导入路径类似 `github.com/gpmgo/gopm` 则应该使用 `path = github.com/gpmgo/gopm` 而不是 `path = gopm`。

## 构建项目

### 默认配置

现在让我们先基于默认设定来构建这个项目，也就是全部使用最新版本的依赖包。

	$ gopm build
	
当命令执行成功时，不会输出任何内容。但如果您想要查看详细信息，则可以通过选项 `-v` 实现：

	$ gopm build -v
	
下面是一个输出样例：

```
[GOPM] 14-09-17 17:40:11 [ INFO] Local repository path: /Users/jiahuachen/.gopm/repos
[GOPM] 14-09-17 17:40:11 [ INFO] Indicated GOPATH: /Users/jiahuachen/Applications/Go
[GOPM] 14-09-17 17:40:11 [DEBUG] Linking demo...
[GOPM] 14-09-17 17:40:11 [DEBUG] Loading dependencies...
[GOPM] 14-09-17 17:40:11 [ INFO] Building...
[GOPM] 14-09-17 17:40:11 [ INFO] Setting GOPATH to /Users/jiahuachen/demo/.vendor
[GOPM] 14-09-17 17:40:11 [ INFO] ===== application outputs start =====

[GOPM] 14-09-17 17:40:11 [ INFO] ====== application outputs end ======
[GOPM] 14-09-17 17:40:11 [ INFO] Setting GOPATH back to /Users/jiahuachen/Applications/Go
[GOPM] 14-09-17 17:40:11 [ INFO] Command executed successfully!
```
	
正如您所看到的，由于我的 `$GOPATH` 中已经下载了最新版本的 beego 及其依赖包，而且我没有指定任何特殊版本，因此 gopm 不会对它们进行链接操作。

现在执行以下指令：

	$ ./demo
	
您应该看到类似下面的输出：

	beego version: 1.4.0
	
### 自定义配置

假如说由于 beego 的 API 破坏，我们需要基于 `v0.9.0` 版本的 beego 构建我们的项目，所以我们需要将 gopmfile 修改为以下内容：

	[target]
	path = demo
	
	[deps]
	github.com/astaxie/beego = tag:v0.9.0
	
在节 `deps` 中我们指示我们需要的 beego 版本为 `tag:v0.9.0`。

下载依赖并重新构建我们的项目，然后运行：
	
	$ gopm get
	$ gopm build
	$ ./demo
	
同样的，您可以用过 `-v` 选项来查看详细信息：

```
[GOPM] 14-09-17 18:07:28 [ INFO] Local repository path: /Users/jiahuachen/.gopm/repos
[GOPM] 14-09-17 18:07:28 [ INFO] Indicated GOPATH: /Users/jiahuachen/Applications/Go
[GOPM] 14-09-17 18:07:28 [DEBUG] Linking demo...
[GOPM] 14-09-17 18:07:28 [DEBUG] Loading dependencies...
[GOPM] 14-09-17 18:07:28 [DEBUG] Linking github.com/astaxie/beego.v0.9.0...
[GOPM] 14-09-17 18:07:28 [DEBUG] Linking github.com/garyburd/redigo...
[GOPM] 14-09-17 18:07:28 [ WARN] Getting imports: no buildable Go source files in /Users/jiahuachen/demo/.vendor/src/github.com/garyburd/redigo
[GOPM] 14-09-17 18:07:28 [ INFO] Building...
[GOPM] 14-09-17 18:07:28 [ INFO] Setting GOPATH to /Users/jiahuachen/demo/.vendor
[GOPM] 14-09-17 18:07:28 [ INFO] ===== application outputs start =====

[GOPM] 14-09-17 18:07:29 [ INFO] ====== application outputs end ======
[GOPM] 14-09-17 18:07:29 [ INFO] Setting GOPATH back to /Users/jiahuachen/Applications/Go
[GOPM] 14-09-17 18:07:29 [ INFO] Command executed successfully!
```
	
值得注意的是，gopm 为了下载了 3 个包（到 gopm 本地仓库），分别是 `github.com/astaxie/beego` 和 `github.com/garyburd/redigo` 这几个我并没有安装在我的电脑上，以及忽略了我已经安装（在 `$GOPATH`）的包 `code.google.com/p/vitess/go/memcache`。

这个例子充分说明了 gopm 能够很好地与 `$GOPATH` 共同协作。

现在，输出应该变成以下内容：

	Beego version: 0.9.0
	
很好很强大，你说是不是！