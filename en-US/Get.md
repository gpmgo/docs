Command get
====

Help information: `gopm get -h` or `gopm help get`:

	NAME:
	   get - fetch remote package(s) and dependencies to local repository
	
	USAGE:
	   command get [command options] [arguments...]
	
	DESCRIPTION:
	   Command get fetches a package, and any pakcages that it depents on.
	If the package has a gopmfile, the fetch process will be driven by that.
	
	gopm get
	gopm get <import path>@[<tag|commit|branch>:<value>]
	gopm get <package name>@[<tag|commit|branch>:<value>]
	
	Can specify one or more: gopm get beego@tag:v0.9.0 github.com/beego/bee
	
	If no argument is supplied, then gopmfile must be present
	
	OPTIONS:
	   --gopath	download package(s) to GOPATH
	   --force	force to update pakcage(s) and dependencies
	   --example	download dependencies for example(s)
   
### `gopm get`

- Feature: Fetch remote package(s) and dependencies to local repository according to gopmfile.
- Example: `gopm get`.

### `gopm get <import path>@[<tag|commit|branch>:<value>]`

- Feature: Fetch remote package(s) and dependencies to local repository according to specified version.
- Example:
	- Latest version: `gopm get github.com/lunny/xorm`.
	- Certain branch: `gopm get github.com/lunny/xorm@branch:master`.
	- Specified tag: `gopm get github.com/lunny/xorm@tag:v0.2.3`.
	- Fixed commit: `gopm get github.com/lunny/xorm@commit:6ffffe9`.
	
### `gopm get <package name>@[<tag|commit|branch>:<value>]`

- Feature: Fetch remote package(s) and dependencies to local repository according to specified version; but instead of using full import path, use project name.
- Example:
	- Latest version: `gopm get xorm`.
	- Certain branch: `gopm get xorm@branch:master`.
	- Specified tag: `gopm get xorm@tag:v0.2.3`.
	- Fixed commit: `gopm get xorm@commit:6ffffe9`.
	
See [well-known Go projects list](../pkgname.list) for details.

## Options

- `-gopath`: download package(s) and dependencies to GOPATH.
- `-force`: force to update pakcage(s) and dependencies.
- `-example`: download dependencies for example(s).