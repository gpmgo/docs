Overview
====

Gopm(Go Package Manager) is a Go package manage tool for search, install, update and share packages in Go.

## Requirements

- Go Development Environment >= 1.1.

## Installation

We use [gobuild](http://build.gopm.io) to do online cross-platform compile work, you can see the full available binary list [here](http://gobuild.io/download/github.com/gpmgo/gopm).

### Install from source code

	go get -u github.com/gpmgo/gopm

The executable will be produced under `$GOPATH/bin` in your file system; for global use purpose, we recommand you to add this path into your `PATH` environment variable.

## Features

- No requirement for installing any version control system tool like `git`, `svn` or `hg` in order to download packages.
- Download, install or build your packages with specific revisions.
- When build program with `gopm build` or `gopm install`, everything just happen in its own GOPATH and do not bother anything you've done unless you told to.
- Put your Go projects on anywhere you want(through gopmfile).

## Index

- [Quick start](Quickstart.md)
- [Command get](Get.md)
- [Command bin](Bin.md)
- [Command gen](Gen.md)
- [Commnad run](Run.md)
- [Command build](Build.md)
- [Commnad install](Install.md)
- [Commnad update](Update.md)
- [gopmfile](gopmfile.md)