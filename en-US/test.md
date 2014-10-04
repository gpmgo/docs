Command test
============

Help information: `gopm test -h` or `gopm help test`:

```
NAME:
   test - link dependencies and go test

USAGE:
   command test [command options] [arguments...]

DESCRIPTION:
   Command test links dependencies according to gopmfile,
and execute 'go test'

gopm test <go test commands>

OPTIONS:
   --tags 		apply build tags
   --verbose, -v	show process details
```
   
### `gopm test <go test commands>`

- Feature: Link dependencies according to gopmfile and go test.
- Example: `gopm test`.

## Options

- `--tags`: apply build tags.
- `--verbose, -v`: show process details.