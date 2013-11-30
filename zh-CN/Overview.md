概览
====

Gopm(Go 包管理工具) 是一个用于搜索、安装、更新和分享 Go 包的管理工具。

## 环境要求

- Go 开发环境版本 >= 1.1。
- 在 Mac OS 或 Unix 类系统下支持命令 `ln -s`。
- 在 Windows 系统下支持命令 `mklink -j`（ **Windows Vista 或更高** ）。

## 安装步骤

因为我们暂时不提供二进制的发布，因此您必须在使用 gopm 之前安装 Go 开发环境 1.1 或更高。

```
go get github.com/gpmgo/gopm
```

可执行文件将会生成在 `$GOPATH/bin` 目录下；为了更加方便的全局调用，我们建议您将该目录增加到 `PATH` 环境变量中。

## 功能特性

- 无需安装 `git`、`svn` 或 `hg` 版本管理工具即可下载包（尽管您目前需要安装 git 工具以通过 `go get` 安装 gopm）。
- 基于指定版本来下载、安装或构建您的包。
- 在您未授权的情况下，`gopm build` 或 `gopm install` 命令的任何操作都发生在自身的 GOPATH 中而不会影响到您在全局 GOPATH 中的任何现有工作。
- 您可以将您的 Go 项目置于任意目录。

## 文档索引

- [快速入门](quickstart.md)
- [get 命令](get.md)
- [bin 命令](bin.md)
- [gen 命令](gen.md)
- [run 命令](run.md)
- [build 命令](build.md)
- [install 命令](install.md)
- [gopmfile](gopmfile.md)