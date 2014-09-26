Command bin
===========

Help information: `gopm bin -h` or `gopm help bin`:

```
NAME:
   bin - download and link dependencies and build binary

USAGE:
   command bin [command options] [arguments...]

DESCRIPTION:
   Command bin downloads and links dependencies according to gopmfile,
and build executable binary to work directory

gopm bin <import path>@[<tag|commit|branch>:<value>]
gopm bin <package name>@[<tag|commit|branch>:<value>]

Can only specify one each time, and only works for projects that
contain main package

OPTIONS:
   --tags 		apply build tags
   --dir, -d './'	build binary to given directory
   --update, -u		update pakcage(s) and dependencies if any
   --remote, -r		build with pakcages in gopm local repository only
   --verbose, -v	show process details
```
   
### `gopm bin <import path>@[<tag|commit|branch>:<value>]`

- Feature: Download and link dependencies and build executable binary according to specified version.
- Detail: Download given package and just get binary without bothering any source code manually.
- Example:
	- Latest version: `gopm bin github.com/gpmgo/gopm`.
	- Certain branch: `gopm bin github.com/gpmgo/gopm@branch:master`.
	- Specified tag: `gopm bin github.com/gpmgo/gopm@tag:v0.1.0`.
	- Fixed commit: `gopm bin github.com/gpmgo/gopm@commit:23ce93a`.
	
#### Usage example

In case you want to build binary to specified path, you can use option `--dir, -d` to achieve that. For example, I want to build gopm to `$GOROOT/bin`, then I should execute `gopm bin -d $GOROOT/bin github.com/gpmgo/gopm`.

##### Latest version: `gopm bin github.com/gpmgo/gopm`

This downloads the latest version of gopm and build it into work directory.

##### Certain branch: `gopm bin github.com/gpmgo/gopm@branch:master`

This downloads the latest version of gopm in master branch and build it into work directory.

##### Specified tag: `gopm bin github.com/gpmgo/gopm@tag:v0.1.0`

This downloads the version of gopm in `tag:v0.1.0` and build it into work directory.

##### Fixed commit: `gopm bin github.com/gpmgo/gopm@commit:23ce93a`

This downloads the version of gopm in `commit:23ce93a` and build it into work directory.
	
### `gopm bin <package name>@[<tag|commit|branch>:<value>]`

- Feature: Download and link dependencies and build executable binary according to specified version; but instead of using full import path, use project name.
- Detail: It's basically a short-cut for package import path.
- Example:
	- Latest version: `gopm bin gopm`.
	- Certain branch: `gopm bin gopm@branch:master`.
	- Specified tag: `gopm bin gopm@tag:v0.1.0`.
	- Fixed commit: `gopm bin gopm@commit:23ce93a`.
	
See [well-known Go projects list](../pkgname.list) for details.

## Options

- `--tags`: apply build tags.
- `-dir, -d`: build binary to given directory.
- `--update, -u`: update pakcage(s) and dependencies if any.
- `--verbose, -v`: show process details.