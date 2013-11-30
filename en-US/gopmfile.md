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