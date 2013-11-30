Overview
====

Gopm(Go Package Manager) is a Go package manage tool for search, install, update and share packages in Go.

## Requirements

- Go Development Environment >= 1.1.
- Command `ln -s` support on Mac OS and Unix-like systems.
- Command `mklink -j` support on Windows( **Windows Vista and later** ).

## Installation

Because we do NOT offer binaries for now, so before you install the gopm, you should have already installed Go Development Environment with version 1.1 and later.

```
go get github.com/gpmgo/gopm
```

The executable will be produced under `$GOPATH/bin` in your file system; for global use purpose, we recommand you to add this path into your `PATH` environment variable.

## Features

- No requirement for installing any version control system tool like `git`, `svn` or `hg` in order to download packages(although you have to install git for installing gopm though `go get` for now).
- Download, install or build your packages with specific revisions.
- When build program with `gopm build` or `gopm install`, everything just happen in its own GOPATH and do not bother anything you've done unless you told to.
- Put your Go projects on anywhere you want.

## Index

- [Quick start](Quickstart.md)
- [Command get](get.md)
- [Command bin](bin.md)
- [Command gen](gen.md)
- [Commnad run](run.md)
- [Command build](build.md)
- [Commnad install](install.md)
- [gopmfile](gopmfile.md)