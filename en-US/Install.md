Command install
===============

Help information: `gopm install -h` or `gopm help install`:

```
NAME:
   install - link dependencies and go install

USAGE:
   command install [command options] [arguments...]

DESCRIPTION:
   Command install links dependencies according to gopmfile,
and execute 'go install'

gopm install

If no argument is supplied, then gopmfile must be present

OPTIONS:
   --tags 		apply build tags
   --remote, -r		build with pakcages in gopm local repository only
   --verbose, -v	show process details
```
   
### `gopm install`

- Feature: Link dependencies according to gopmfile for current project and go install.
- Detail: Download missing dependencies then link and install them.
- Example: `gopm install`.

### `gopm install <import path>`

- Feature: Link dependencies according to gopmfile of given import path and go install.
- Detail: Download missing dependencies then link and install them.
- Example: `gopm install github.com/Unknwon/com`.

## Options

- `--tags`: apply build tags.
- `-verbose`: show process details.