Command list
============

Help information: `gopm list -h` or `gopm help list`:

```
NAME:
   list - list all dependencies of current project

USAGE:
   command list [command options] [arguments...]

DESCRIPTION:
   Command list lsit all dependencies of current Go project

gopm list

Make sure you run this command in the root path of a go project.

OPTIONS:
   --tags 			apply build tags
   --test, -t		show test imports
   --verbose, -v	show process details
```
   
### `gopm list`

- Feature: List all dependencies of current project and shows its reversion if available in gopmfile.
- Example: `gopm list`

#### Usage example

Following content shows an example of `gopm list -v`:

```
[GOPM] 14-09-22 20:48:08 [ INFO] Local repository path: /Users/jiahuachen/.gopm/repos
[GOPM] 14-09-22 20:48:08 [ INFO] Indicated GOPATH: /Users/jiahuachen/Applications/Go
Dependency list(20):
-> github.com/Unknwon/cae @ commit:2e70a1351b
-> github.com/Unknwon/com @ commit:2cbcbc6916
-> github.com/Unknwon/goconfig @ commit:0f8d8dc1c0
-> github.com/Unknwon/i18n @ commit:47baeff8d0
-> github.com/Unknwon/macaron
-> github.com/codegangsta/cli @ commit:7381bc4e62
-> github.com/go-sql-driver/mysql @ commit:8111ee3ec3
-> github.com/go-xorm/core @ commit:750aae0fa5
-> github.com/go-xorm/xorm @ commit:2d8b3135b1
-> github.com/gogits/gfm @ commit:40f747a9c0
-> github.com/gogits/oauth2 @ commit:99cbec870a
-> github.com/lib/pq @ commit:b021d0ef20
-> github.com/macaron-contrib/cache @ commit:204d8e5137
-> github.com/macaron-contrib/captcha
-> github.com/macaron-contrib/csrf
-> github.com/macaron-contrib/i18n
-> github.com/macaron-contrib/session
-> github.com/macaron-contrib/toolbox @ commit:57127bcc89
-> github.com/nfnt/resize @ commit:581d15cb53
-> github.com/saintfish/chardet @ commit:3af4cd4741
```

## Options

- `--tags`: apply build tags.
- `--test, -t`: list dependencies of test files.
- `--verbose, -v`: show process details.