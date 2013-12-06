Command install
====

Help information: `gopm install -h` or `gopm help install`:

	NAME:
	   install - link dependencies and go install
	
	USAGE:
	   command install [command options] [arguments...]
	
	DESCRIPTION:
	   Command install links dependencies according to gopmfile,
	and execute 'go install'
	
	gopm install
	gopm install <import path>
	
	If no argument is supplied, then gopmfile must be present
	
	OPTIONS:
	   --pkg, -p		only install non-main packages
	   --verbose, -v	show process details
   
### `gopm install`

- Feature: Link dependencies according to gopmfile for current project and go install.
- Example: `gopm install`.

### `gopm install <import path>`

- Feature: Link dependencies according to gopmfile of given import path and go install.
- Example: `gopm install github.com/Unknwon/com`.

## Options

- `--pkg, -p`: only install non-main packages.
- `-verbose`: show process details.