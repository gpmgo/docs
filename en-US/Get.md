Command get
====

Help information: `gopm get -h` or `gopm help get`:

	NAME:
	   get - fetch remote package(s) and dependencies to local repository
	
	USAGE:
	   command get [command options] [arguments...]
	
	DESCRIPTION:
	   Command get fetches a package, and any pakcage that it depents on.
	If the package has a gopmfile, the fetch process will be driven by that.
	
	gopm get
	gopm get <import path>@[<tag|commit|branch>:<value>]
	gopm get <package name>@[<tag|commit|branch>:<value>]
	
	Can specify one or more: gopm get beego@tag:v0.9.0 github.com/beego/bee
	
	If no version specified and package exists in GOPATH,
	it will be skipped unless user enabled '--remote, -r' option
	then all the packages go into gopm local repository.
	
	OPTIONS:
	   --gopath, -g		download all pakcages to GOPATH
	   --update, -u		update pakcage(s) and dependencies if any
	   --example, -e	download dependencies for example folder
	   --remote, -r		download all pakcages to gopm local repository
	   --verbose, -v	show process details
   
### `gopm get`

- Feature: Fetch remote package(s) and dependencies to local repository according to gopmfile.
- Detail: No argument means get dependencies for project that is in work directory, if a gopmfile is supplied, then will get based on the information from gopmfile.
- Example: `gopm get`.

#### Usage cases

##### `gopm get`

Suppose your work directory is in the project of gopm(`github.com/gpmgo/gopm`):

	$ pwd
	
Output: 

	$GOPATH/src/github.com/gpmgo/gopm

And there is a gopmfile:

	$ cat .gopmfile
	
Output:

	[target]
	path=github.com/gpmgo/gopm
	
	[deps]
	github.com/codegangsta/cli=
	github.com/Unknwon/com=
	github.com/Unknwon/goconfig=
	github.com/aybabtme/color=
	
So the command will downloads 4 packages(into gopm local repository `~/.gopm/repos`) in `deps` section if there do not exist in your `$GOPATH`.

Suppose you need to download them all into your GOPATH so you may able to make some changes and then compile gopm. Use option `--gopath, -g` to achieve that.

However, in case you want to keep your `$GOPATH` clean and download all of them into gopm local repository. Use option `--remote, -r` to achieve that.

### `gopm get <import path>@[<tag|commit|branch>:<value>]`

- Feature: Fetch remote package(s) and dependencies to local repository according to specified version.
- Detail: This command can accept one or more import paths with/without specified version.
- Example:
	- Latest version: `gopm get github.com/lunny/xorm`.
	- Certain branch: `gopm get github.com/lunny/xorm@branch:master`.
	- Specified tag: `gopm get github.com/lunny/xorm@tag:v0.2.3`.
	- Fixed commit: `gopm get github.com/lunny/xorm@commit:6ffffe9`.

#### Usage cases

##### Latest version: `gopm get github.com/lunny/xorm`

This downloads the latest version of xorm, and its dependencies according to its gopmfile.

##### Certain branch: `gopm get github.com/lunny/xorm@branch:master`

This downloads the latest version of xorm in master branch, and its dependencies according to its gopmfile.

##### Specified tag: `gopm get github.com/lunny/xorm@tag:v0.2.3`

This downloads the version of xorm in `tag:v0.2.3`, and its dependencies according to its gopmfile.

##### Fixed commit: `gopm get github.com/lunny/xorm@commit:6ffffe9`

This downloads the version of xorm in `commit:6ffffe9`, and its dependencies according to its gopmfile.
	
### `gopm get <package name>@[<tag|commit|branch>:<value>]`

- Feature: Fetch remote package(s) and dependencies to local repository according to specified version; but instead of using full import path, use project name.
- Detail: It's basically a short-cut for package import path.
- Example:
	- Latest version: `gopm get xorm`.
	- Certain branch: `gopm get xorm@branch:master`.
	- Specified tag: `gopm get xorm@tag:v0.2.3`.
	- Fixed commit: `gopm get xorm@commit:6ffffe9`.
	
See [well-known Go projects list](../pkgname.list) for details.

## Options

- `--gopath, -g	`: download all pakcages to GOPATH.
- `--update, -u`: update pakcage(s) and dependencies if any.
- `--example, -e`: download dependencies for example folder.
- `--remote, -r`: download all pakcages to gopm local repository.
- `--verbose, -v`: show process details