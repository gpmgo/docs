Command gen
====

Help information: `gopm gen -h` or `gopm help gen`:

	NAME:
	   gen - generate a gopmfile according current Go project
	
	USAGE:
	   command gen [command options] [arguments...]
	
	DESCRIPTION:
	   Command gen gets dependencies and generates a gopmfile
	
	gopm gen
	
	Make sure you run this command in the root path of a go project.
	
	OPTIONS:
	   --example, -e	check dependencies for example(s)
	   --verbose, -v	show process details
   
### `gopm gen`

- Feature: Generate a gopmfile according current Go project.
- Detail: Get dependencies and list in the gopmfile. 
- Example: `gopm gen`.

#### Usage cases

I'm now under `$GOPATH/src/github.com/beego/beeweb`, and I want to generate a gopmfile:

	$ gopm gen
	$ cat .gopmfile
	
Output:

	[deps]
	github.com/astaxie/beego=
	github.com/beego/i18n=
	github.com/Unknwon/com=
	github.com/Unknwon/goconfig=
	github.com/slene/blackfriday=	

Notice that it only gets the direct-dependencies, which it does not care the dependencies of beego, i18n, com, etc. Because that's the responsibilities of the package author.

More information about how to write versions, please see [gopmfile](Gopmfile.md).

## Options

- `-example`: check dependencies for example(s).
- `--verbose, -v`: show process details.