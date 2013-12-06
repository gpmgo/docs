Quick start
====

In this section, we're going to demonstrate a simple usage of gopm, which uses two different versions of beego then prints the version of beego in the application.

## Setup

You do not have to put this project under GOPATH, so let's pick `~/demo` as our project root path:

	$ mkdir ~/demo
	$ cd ~/demo
	
Now, create a `main.go`:

	$ touch main.go
	
Copy and paste following code:

```go
package main

import (
	"github.com/astaxie/beego"
)

func main() {
	println("Beego version:", beego.VERSION)
}
```

Well done!

## gopmfile

This file contains all the information that gopm needs, so let's see what can we do in this demo.

First, create `.gopmfile` in project root path:

	$ touch .gopmfile
	
Good, copy and paste following content into file:

	[target]
	path=demo
	
Key `path` indicates the project name. 

**ATTENTION** If you're working on the project that has import path like `github.com/gpmgo/gopm`, you should use `path=github.com/gpmgo/gopm` instead of `path=gopm`.

## Build

### Default

Let's build with all default setting, which uses all latest version of all dependencies.

	$ gopm build
	
If the command executed successfully, nothing will be printed; however, if you want to see details, you can add option `-v` like follows:

	$ gopm build -v
	
Following content is a sample output:

	gopm INFO Indicated GOPATH: /Users/jiahuachen/Applications/Go
	gopm TRAC Loading gopmfile...
	gopm INFO Target name: demo
	gopm INFO Linking demo
	gopm TRAC Building...
	gopm INFO Changing work directory to /Users/jiahuachen/demo/.vendor/src/demo
	gopm INFO Setting GOPATH to /Users/jiahuachen/demo/.vendor
	gopm INFO ===== application outputs start =====
	
	gopm INFO
	====== application outputs end ======
	gopm INFO Setting GOPATH back to /Users/jiahuachen/Applications/Go
	gopm INFO Changing work directory back to /Users/jiahuachen/demo
	gopm SUCC build Command executed successfully!
	
As you can see, because my GOPATH already has latest version of package beego and its dependencies, and I haven't specified any version, so gopm will not link them.

Now run it:

	$ ./demo
	
And you should see something like:

	beego version: 0.9.9
	
### Customize

Let's say we want to build with `beego v0.9.0` due to some API breaks, so we want to change our gopmfile to be like follows:

	[target]
	path=demo
	
	[deps]
	github.com/astaxie/beego=tag:v0.9.0
	
In section `deps`, we indicate beego version to be at `tag:v0.9.0`.

Rebuild our application and run it:

	$ gopm build
	$ ./demo
	
Again, you can use `-v` option to see details:

	gopm INFO Indicated GOPATH: /Users/jiahuachen/Applications/Go
	gopm TRAC Loading gopmfile...
	gopm INFO Target name: demo
	gopm MSG! Downloading package: github.com/astaxie/beego@tag:v0.9.0
	gopm TRAC Skipped installed package: code.google.com/p/vitess/go/memcache@branch:<UTD>
	gopm MSG! Downloading package: github.com/garyburd/redigo/redis@branch:<UTD>
	gopm SUCC GET github.com/garyburd/redigo@branch:<UTD>
	gopm TRAC Skipped installed package: github.com/garyburd/redigo/redis@branch:<UTD>
	gopm MSG! Downloading package: github.com/go-sql-driver/mysql@branch:<UTD>
	gopm SUCC GET github.com/go-sql-driver/mysql@branch:<UTD>
	gopm SUCC GET github.com/astaxie/beego@tag:v0.9.0
	gopm INFO Linking github.com/astaxie/beego.v0.9.0
	gopm INFO Linking github.com/garyburd/redigo
	gopm INFO Linking github.com/go-sql-driver/mysql
	gopm INFO Linking demo
	gopm TRAC Building...
	gopm INFO Changing work directory to /Users/jiahuachen/demo/.vendor/src/demo
	gopm INFO Setting GOPATH to /Users/jiahuachen/demo/.vendor
	gopm INFO ===== application outputs start =====
	
	gopm INFO ====== application outputs end ======
	gopm INFO Setting GOPATH back to /Users/jiahuachen/Applications/Go
	gopm INFO Changing work directory back to /Users/jiahuachen/demo
	gopm SUCC build Command executed successfully!
	
Notice here gopm downloads three packages for me(into gopm local repository), which are `github.com/astaxie/beego`, `github.com/garyburd/redigo/redis` and `github.com/go-sql-driver/mysql` that I didn't install in my computer, and skipped package `code.google.com/p/vitess/go/memcache` that has been already installed(in my GOPATH).

This case shows how gopm works well with your GOPATH.
	
Now, the output should be:

	Beego version: 0.9.0
	
Simple and cool, doesn't it?