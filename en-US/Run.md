Command run
===========

Help information: `gopm run -h` or `gopm help run`:

```
NAME:
   run - link dependencies and go run

USAGE:
   command run [command options] [arguments...]

DESCRIPTION:
   Command run links dependencies according to gopmfile,
and execute 'go run'

gopm run <go run commands>
gopm run -l will recursively find .gopmfile with value localPath
and run the cmd in the .gopmfile, Windows hasn't supported yet,
you need to run the command right at the local_gopath dir.
```
   
### `gopm run <go run commands>`

- Feature: Link dependencies according to gopmfile and go run.
- Example: `gopm run main.go`.

## Options

- `--tags`: apply build tags.
- `--verbose, -v`: show process details.