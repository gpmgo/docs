概览
====

Gopm(Go 包管理工具) 是一个用于搜索、安装、更新和分享 Go 包的管理工具。

## 环境要求

- Go 开发环境版本 >= 1.1。

## 安装步骤

我们使用 [gobuild](http://build.gopm.io) 来完成在线跨平台编译工作，您可以在 [这里](http://gobuild.io/download/github.com/gpmgo/gopm) 找到完整的二进制下载列表。

### 通过源码安装

	go get -u github.com/gpmgo/gopm

可执行文件将会生成在 `$GOPATH/bin` 目录下；为了更加方便的全局调用，我们建议您将该目录增加到 `PATH` 环境变量中。

## 功能特性

- 无需安装 `git`、`svn` 或 `hg` 版本管理工具即可下载包（尽管您目前需要安装 git 工具以通过 `go get` 安装 gopm）。
- 基于指定版本来下载、安装或构建您的包。
- 在您未授权的情况下，`gopm build` 或 `gopm install` 命令的任何操作都发生在自身的 GOPATH 中而不会影响到您在全局 GOPATH 中的任何现有工作。
- 您可以将您的 Go 项目置于任意目录（通过 gopmfile）。

## 文档索引

- [快速入门](Quickstart.md)
- [get 命令](Get.md)
- [bin 命令](Bin.md)
- [gen 命令](Gen.md)
- [run 命令](Run.md)
- [build 命令](Build.md)
- [install 命令](Install.md)
- [update 命令](Update.md)
- [gopmfile](gopmfile.md)