Quick start
====

In this section, we're going to demonstrate a simple usage of gopm, which uses two different versions of beego then prints the version of beego in the application.

## Setup

You do not have put this project under GOPATH, so let's pick `~/demo` as our project root path:

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
	
Following content is a sample output:

	gopm TRAC Loading gopmfile...
	gopm INFO Target name: demo
	gopm INFO Linking github.com/wendal/errors
	gopm INFO Linking github.com/astaxie/beego
	gopm INFO Linking github.com/clbanning/x2j
	gopm INFO Linking github.com/wendal/goyaml2
	gopm INFO Linking github.com/garyburd/redigo/redis
	gopm INFO Linking github.com/go-sql-driver/mysql
	gopm INFO Linking demo
	gopm TRAC Building...
	gopm INFO Changing work directory to /Users/jiahuachen/demo/vendor/src/demo
	gopm INFO Setting GOPATH to /Users/jiahuachen/demo/vendor
	gopm INFO ===== application outputs start =====
	
	
	gopm INFO ====== application outputs end ======
	gopm INFO Setting GOPATH back to /Users/jiahuachen/Applications/Go
	gopm INFO Changing work directory back to /Users/jiahuachen/demo
	gopm SUCC Build Command execute successfully!
	
Good so far, now run it:

	$ ./demo
	
And you should see something like:

	beego version: 0.9.9
	
### Customize

Let's say we want to build with beego v0.9.0 due to some API breaks, so we want to change our gopmfile to be like follows:

	[target]
	path=demo
	
	[deps]
	github.com/astaxie/beego=tag:v0.9.0
	
In section `deps`, we indicate beego version to be at `tag:v0.9.0`.

Rebuild our application and run it:

	$ gopm build
	$ ./demo
	
Now, the output should be:

	Beego version: 0.9.0
	
Simple and cool, doesn't it?