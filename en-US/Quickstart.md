Quick Start
===========

In this section, we're going to demonstrate a simple usage of gopm, which uses two different versions of beego then prints the version of beego in the application.

## Setup

You do not have to put this project under `$GOPATH`, so let's pick `~/demo` as our project root path:

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
	path = demo
	
Key `path` indicates the project name. 

**ATTENTION** If you're working on the project that has import path like `github.com/gpmgo/gopm`, you should use `path = github.com/gpmgo/gopm` instead of `path = gopm`.

## Build

### Default

Let's build with all default setting, which uses all latest version of all dependencies.

	$ gopm build
	
If the command executed successfully, nothing will be printed; however, if you want to see details, you can add option `-v` like follows:

	$ gopm build -v
	
Following content is a sample output:

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
	
As you can see, because my `$GOPATH` already has latest version of package beego and its dependencies, and I haven't specified any version, so gopm will not link them.

Now run it:

	$ ./demo
	
And you should see something like:

	beego version: 1.4.0
	
### Customize

Let's say we want to build with `beego v0.9.0` due to some API breaks, so we want to change our gopmfile to be like follows:

	[target]
	path = demo
	
	[deps]
	github.com/astaxie/beego = tag:v0.9.0
	
In section `deps`, we indicate beego version to be at `tag:v0.9.0`.

Download dependency, rebuild our application and run it:

	$ gopm get
	$ gopm build
	$ ./demo
	
Again, you can use `-v` option to see details:

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
	
Here gopm downloads three packages for me(into gopm local repository), which are `github.com/astaxie/beego` and `github.com/garyburd/redigo` that I didn't install in my computer, and skipped package `code.google.com/p/vitess/go/memcache` that has been already installed(in my `$GOPATH`).

This case shows how gopm works well with your `$GOPATH`.
	
Now, the output should be:

	Beego version: 0.9.0
	
Simple and cool, doesn't it?