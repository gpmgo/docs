gopmfile
====
The gopmfile need to be put under root path of project, and named `.gopmfile`.

A sample gopmfile:

    [target]
	path=github.com/gpmgo/gopm
	
	[deps]
	github.com/codegangsta/cli=branch:master

- `target -> path` indicates the project name or import path.
- `deps` section contains special(non-latest) versions dependencies.

## How to write package version

There are 5 possible patterns for package version:

- Blank: which means always build with latest version of dependency.
- `/path/to/my/project`：directory path, for example: `d:\projects\xorm`.
- `branch:<value>`: certain branch, for example: `branch:master`.
- `tag:<value>`: specified tag, for example: `tag:v0.9.0`.
- `commit:<value>`: fixed commit, for example: `commit:6ffffe9`. Usually only first 7 letters of SHA is enough to determine a commit.
