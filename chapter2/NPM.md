# what's npm
npm is the package manager for javascript
# Installing npm
The npm command-line tool is bundled with Node.js. If you have it installed, then you already have npm. If not, download Node.js below:	[Download Node.js](https://nodejs.org/en/download/)
# Documentation & screencasts
We've got a docs site featuring videos and tutorials to help you make your javascript dreams come true. Head on over to the docs site:	[View the Docs](https://docs.npmjs.com/)
# Study List
* [npm Documentation](https://docs.npmjs.com/)
# 注册用户和用户登录
* npm adduser
```
[root@myServer project count_sheep]# npm adduser xuliehao
Username: xuliehao
Password: 
Email: (this IS public) 997948809@163.com
Logged in as xuliehao on https://registry.npmjs.org/.
```
* 账号注册成功可以登录了，去邮箱查看验证邮件，通过邮件验证
* npm login
```
[root@myServer project count_sheep]# npm login
Username: xuliehao
Password: 
Email: (this IS public) 997948809@163.com
Logged in as xuliehao on https://registry.npmjs.org/.
```
# 获取配置文件命令
* npm config get globalconfig
```
---window---
$ npm config get globalconfig
C:\Users\Administrator\AppData\Roaming\npm\etc\npmrc
---linux---
npm config get globalconfig
/usr/local/yanhu/nodejs/node-v6.9.4-linux-x64/etc/npmrc
```
* npm config get userconfig
```
---window---
$ npm config get userconfig
C:\Users\Administrator\.npmrc
---linux---
npm config get userconfig
/root/.npmrc
```
# command-line
* npm set registry
```
npm set registry "https://registry.npmjs.org/"
npm set registry "http://xnpm.repo.xunlei.cn/"
npm set registry "https://registry.npm.taobao.org"
```
* npm config set registry
```
npm config set registry https://registry.npmjs.org/
npm config set registry http://xnpm.repo.xunlei.cn/
npm config set registry https://registry.npm.taobao.org
```
* npm config get registry
```
$ npm config get registry
ttps://registry.npm.taobao.org
```
* npm config --help

```
$ npm config --help
npm config set <key> <value>
npm config get [<key>]
npm config delete <key>
npm config list [--json]
npm config edit
npm set <key> <value>
npm get [<key>]

alias: c
```
* npm config --list

```
$ npm config list
; cli configs
metrics-registry = "https://registry.npm.taobao.org/"
scope = ""
user-agent = "npm/5.8.0 node/v8.9.3 win32 x64"

; userconfig C:\Users\Administrator\.npmrc
init.author.email = "997948809@163.com"
init.author.name = "luojianet"
list = ""
loglevel = "http"
registor = ""
registry = "https://registry.npm.taobao.org/"

; builtin config undefined
prefix = "C:\\Users\\Administrator\\AppData\\Roaming\\npm"

; node bin location = C:\Program Files\nodejs\node.exe
; cwd = C:\github\npm
; HOME = C:\Users\Administrator
; "npm config ls -l" to show all defaults.
```
* npm config list -l

```
$ npm config list -l
; cli configs
long = true
metrics-registry = "ttps://registry.npm.taobao.org"
scope = ""
user-agent = "npm/5.8.0 node/v8.9.3 win32 x64"

; userconfig C:\Users\Administrator\.npmrc
init.author.email = "997948809@163.com"
init.author.name = "luojianet"
list = ""
loglevel = "http"
registor = ""
registry = "ttps://registry.npm.taobao.org"

; builtin config undefined
prefix = "C:\\Users\\Administrator\\AppData\\Roaming\\npm"

; default values
access = null
allow-same-version = false
also = null
always-auth = false
auth-type = "legacy"
bin-links = true
browser = null
ca = null
cache = "C:\\Users\\Administrator\\AppData\\Roaming\\npm-cache"
cache-lock-retries = 10
cache-lock-stale = 60000
cache-lock-wait = 10000
cache-max = null
cache-min = 10
cafile = undefined
cert = null
cidr = null
color = true
commit-hooks = true
depth = null
description = true
dev = false
dry-run = false
editor = "notepad.exe"
engine-strict = false
fetch-retries = 2
fetch-retry-factor = 10
fetch-retry-maxtimeout = 60000
fetch-retry-mintimeout = 10000
force = false
git = "git"
git-tag-version = true
global = false
global-style = false
globalconfig = "C:\\Users\\Administrator\\AppData\\Roaming\\npm\\etc\\npmrc"
globalignorefile = "C:\\Users\\Administrator\\AppData\\Roaming\\npm\\etc\\npmignore"
group = 0
ham-it-up = false
heading = "npm"
https-proxy = null
if-present = false
ignore-prepublish = false
ignore-scripts = false
init-author-email = ""
init-author-name = ""
init-author-url = ""
init-license = "ISC"
init-module = "C:\\Users\\Administrator\\.npm-init.js"
init-version = "1.0.0"
json = false
key = null
legacy-bundling = false
link = false
local-address = undefined
; loglevel = "notice" (overridden)
logs-max = 10
; long = false (overridden)
maxsockets = 50
message = "%s"
; metrics-registry = null (overridden)
no-proxy = null
node-options = null
node-version = "8.9.3"
offline = false
onload-script = null
only = null
optional = true
otp = 0
package-lock = true
package-lock-only = false
parseable = false
prefer-offline = false
prefer-online = false
; prefix = "C:\\Program Files\\nodejs" (overridden)
production = false
progress = true
proxy = null
read-only = false
rebuild-bundle = true
; registry = "https://registry.npmjs.org/" (overridden)
rollback = true
save = true
save-bundle = false
save-dev = false
save-exact = false
save-optional = false
save-prefix = "^"
save-prod = false
scope = ""
script-shell = null
scripts-prepend-node-path = "warn-only"
searchexclude = null
searchlimit = 20
searchopts = ""
searchstaleness = 900
send-metrics = false
shell = "C:\\Windows\\system32\\cmd.exe"
shrinkwrap = true
sign-git-tag = false
sso-poll-frequency = 500
sso-type = "oauth"
strict-ssl = true
tag = "latest"
tag-version-prefix = "v"
timing = false
tmp = "C:\\Users\\ADMINI~1\\AppData\\Local\\Temp"
umask = 0
unicode = false
unsafe-perm = true
usage = false
user = 0
; user-agent = "npm/{npm-version} node/{node-version} {platform} {arch}" (overridden)
userconfig = "C:\\Users\\Administrator\\.npmrc"
version = false
versions = false
viewer = "browser"
```
* npm whoami
```
$ npm whoami
npm http request GET https://registry.npmjs.org/-/whoami
npm http 200 https://registry.npmjs.org/-/whoami
luojianet
```
* npm view count_sheep

```
$ npm view count_sheep
npm http request GET https://registry.npmjs.org/count_sheep
npm http 200 https://registry.npmjs.org/count_sheep

{ name: 'count_sheep',
  description: 'Count sheep app,For xshell sleep.npm run-script start,npm run-script shram,npm run-script pwd',
  'dist-tags': { latest: '1.0.10', beta: '1.0.6', test: '1.0.5' },
  versions:
   [ '1.0.0',
     '1.0.2',
     '1.0.3',
     '1.0.4',
     '1.0.5',
     '1.0.6',
     '1.0.7',
     '1.0.8',
     '1.0.9',
     '1.0.10' ],
  maintainers: [ 'luojianet <a3729251989@gmail.com>' ],
  time:
   { modified: '2017-08-30T10:33:43.587Z',
     created: '2017-02-02T14:32:39.666Z',
     '1.0.0': '2017-02-02T14:32:39.666Z',
     '1.0.1': '2017-02-03T01:06:37.007Z',
     '1.0.2': '2017-02-03T01:16:12.827Z',
     '1.0.3': '2017-02-03T08:02:23.647Z',
     '1.0.4': '2017-02-03T08:24:23.141Z',
     '1.0.5': '2017-02-03T08:58:15.762Z',
     '1.0.6': '2017-02-03T09:38:19.002Z',
     '1.0.7': '2017-02-03T23:40:28.719Z',
     '1.0.8': '2017-02-03T23:49:13.262Z',
     '1.0.9': '2017-08-29T02:26:30.891Z',
     '1.0.10': '2017-08-29T02:44:59.904Z' },
  homepage: 'https://github.com/luojianet/nodejs#readme',
  keywords: [ 'Count sheep', 'Count star' ],
  repository:
   { type: 'git',
     url: 'git+ssh://git@github.com/luojianet/nodejs.git' },
  author: 'luojianet <a3729251989@gmail.com>',
  bugs: { url: 'https://github.com/luojianet/nodejs/issues' },
  license: 'MIT',
  readmeFilename: 'README.md',
  users: { xuliehao: true },
  bin: { ctsp: './count_sheep.js' },
  bundleDependencies: false,
  deprecated: false,
  main: 'count_sheep.js',
  scripts: { pwd: 'pwd', shram: 'free -m', start: 'ctsp' },
  version: '1.0.10',
  dist:
   { integrity: 'sha512-JX4c2fvuXwJ9bcrUzmxeBGbP+lLALPAi+2uUuShhEp1npEfcW7yfmnCmrswqfdlEZEleHCPQxEI2+0Yp8FKuzA==',
     shasum: '9928cdb7d8ca8059855c60fe3f754bd9ea0e94d3',
     tarball: 'https://registry.npmjs.org/count_sheep/-/count_sheep-1.0.10.tgz' },
  directories: {} }
```
* npm view count_sheep version

```
$ npm view count_sheep version
npm http request GET https://registry.npmjs.org/count_sheep
npm http 200 https://registry.npmjs.org/count_sheep
1.0.10
```
* npm view count_sheep dist

```
$ npm view count_sheep dist
npm http request GET https://registry.npmjs.org/count_sheep
npm http 200 https://registry.npmjs.org/count_sheep

{ integrity: 'sha512-JX4c2fvuXwJ9bcrUzmxeBGbP+lLALPAi+2uUuShhEp1npEfcW7yfmnCmrswqfdlEZEleHCPQxEI2+0Yp8FKuzA==',
  shasum: '9928cdb7d8ca8059855c60fe3f754bd9ea0e94d3',
  tarball: 'https://registry.npmjs.org/count_sheep/-/count_sheep-1.0.10.tgz' }
```
* npm init

```
$ npm init
This utility will walk you through creating a package.json file.
It only covers the most common items, and tries to guess sensible defaults.

See `npm help json` for definitive documentation on these fields
and exactly what they do.

Use `npm install <pkg>` afterwards to install a package and
save it as a dependency in the package.json file.

Press ^C at any time to quit.
package name: (npm)
version: (1.0.0)
entry point: (index.js)
license: (ISC)
About to write to C:\github\npm\package.json:
```
* npm init -y

```
$ npm init -y
Wrote to C:\github\npm\package.json:

{
  "name": "npm",
  "version": "1.0.0",
  "description": "npm command repository",
  "private": true,
  "scripts": {
    "test": "echo \"Error: no test specified\" && exit 1"
  },
  "repository": {
    "type": "git",
    "url": "git+https://github.com/luojianet/npm.git"
  },
  "keywords": [],
  "author": "luojianet <997948809@163.com>",
  "license": "ISC",
  "bugs": {
    "url": "https://github.com/luojianet/npm/issues"
  },
  "homepage": "https://github.com/luojianet/npm#readme",
  "dependencies": {
    "@luojianet/web01": "^1.0.0",
    "count_sheep": "^1.0.8",
    "element-ui": "^1.4.3"
  },
  "main": "index.js",
  "directories": {
    "doc": "docs"
  },
  "devDependencies": {}
}
```

* npm version
```
$ npm version
{ webpack: '4.4.1',
  npm: '5.8.0',
  ares: '1.10.1-DEV',
  cldr: '31.0.1',
  http_parser: '2.7.0',
  icu: '59.1',
  modules: '57',
  nghttp2: '1.25.0',
  node: '8.9.3',
  openssl: '1.0.2n',
  tz: '2017b',
  unicode: '9.0',
  uv: '1.15.0',
  v8: '6.1.534.48',
  zlib: '1.2.11' }
```
* npm publish

```
[root@myServer project count_sheep]# npm publish
+ count_sheep@1.0.10
```
* npm

```
$ npm

Usage: npm <command>

where <command> is one of:
    access, adduser, bin, bugs, c, cache, ci, completion,
    config, ddp, dedupe, deprecate, dist-tag, docs, doctor,
    edit, explore, get, help, help-search, i, init, install,
    install-test, it, link, list, ln, login, logout, ls,
    outdated, owner, pack, ping, prefix, profile, prune,
    publish, rb, rebuild, repo, restart, root, run, run-script,
    s, se, search, set, shrinkwrap, star, stars, start, stop, t,
    team, test, token, tst, un, uninstall, unpublish, unstar,
    up, update, v, version, view, whoami

npm <command> -h     quick help on <command>
npm -l           display full usage info
npm help <term>  search for help on <term>
npm help npm     involved overview

Specify configs in the ini-formatted file:
    C:\Users\Administrator\.npmrc
or on the command line via: npm <command> --key value
Config info can be viewed via: npm help config

npm@5.8.0 C:\Users\Administrator\AppData\Roaming\npm\node_modules\npm
```
* npm -l

```
$ npm -l

Usage: npm <command>

where <command> is one of:

    access       npm access public [<package>]
                 npm access restricted [<package>]
                 npm access grant <read-only|read-write> <scope:team> [<package>]
                 npm access revoke <scope:team> [<package>]
                 npm access ls-packages [<user>|<scope>|<scope:team>]
                 npm access ls-collaborators [<package> [<user>]]
                 npm access edit [<package>]

    adduser      npm adduser [--registry=url] [--scope=@orgname] [--auth-type=legacy] [--always-auth]

                 aliases: login, add-user

    bin          npm bin [--global]

    bugs         npm bugs [<pkgname>]

                 alias: issues

    cache        npm cache add <tarball file>
                 npm cache add <folder>
                 npm cache add <tarball url>
                 npm cache add <git url>
                 npm cache add <name>@<version>
                 npm cache clean
                 npm cache verify

    ci           npm ci

    completion   source <(npm completion)

    config       npm config set <key> <value>
                 npm config get [<key>]
                 npm config delete <key>
                 npm config list [--json]
                 npm config edit
                 npm set <key> <value>
                 npm get [<key>]

                 alias: c

    dedupe       npm dedupe

                 aliases: ddp, find-dupes

    deprecate    npm deprecate <pkg>[@<version>] <message>

    dist-tag     npm dist-tag add <pkg>@<version> [<tag>]
                 npm dist-tag rm <pkg> <tag>
                 npm dist-tag ls [<pkg>]

                 alias: dist-tags

    docs         npm docs <pkgname>
                 npm docs .

                 alias: home

    doctor       npm doctor

    edit         npm edit <pkg>[@<version>]

    explore      npm explore <pkg> [ -- <command>]

    get          npm get <key> <value> (See `npm config`)

    help

    help-search  npm help-search <text>

    init         npm init [--force|-f|--yes|-y]

    install
                 npm install (with no args, in package dir)
                 npm install [<@scope>/]<pkg>
                 npm install [<@scope>/]<pkg>@<tag>
                 npm install [<@scope>/]<pkg>@<version>
                 npm install [<@scope>/]<pkg>@<version range>
                 npm install <folder>
                 npm install <tarball file>
                 npm install <tarball url>
                 npm install <git:// url>
                 npm install <github username>/<github project>

                 aliases: i, isntall, add
                 common options: [--save-prod|--save-dev|--save-optional] [--save-exact] [--no-save]

    install-test
                 npm install-test [args]
                 Same args as `npm install`

                 alias: it

    link         npm link (in package dir)
                 npm link [<@scope>/]<pkg>[@<version>]

                 alias: ln

    logout       npm logout [--registry=<url>] [--scope=<@scope>]

    ls           npm ls [[<@scope>/]<pkg> ...]

                 aliases: list, la, ll

    outdated     npm outdated [[<@scope>/]<pkg> ...]

    owner        npm owner add <user> [<@scope>/]<pkg>
                 npm owner rm <user> [<@scope>/]<pkg>
                 npm owner ls [<@scope>/]<pkg>

                 alias: author

    pack         npm pack [[<@scope>/]<pkg>...]

    ping         npm ping
                 ping registry

    prefix       npm prefix [-g]

    profile      npm profile enable-2fa [auth-only|auth-and-writes]
                 npm profile disable-2fa
                 npm profile get [<key>]
                 npm profile set <key> <value>

    prune        npm prune [[<@scope>/]<pkg>...] [--production]

    publish      npm publish [<tarball>|<folder>] [--tag <tag>] [--access <public|restricted>]

                 Publishes '.' if no argument supplied

                 Sets tag `latest` if no --tag specified

    rebuild      npm rebuild [[<@scope>/<name>]...]

                 alias: rb

    repo         npm repo [<pkg>]

    restart      npm restart [-- <args>]

    root         npm root [-g]

    run-script   npm run-script <command> [-- <args>...]

                 aliases: run, rum

    search       npm search [--long] [search terms ...]

                 aliases: s, se, find

    set          npm set <key> <value> (See `npm config`)

    shrinkwrap   npm shrinkwrap

    star         npm star [<pkg>...]
                 npm unstar [<pkg>...]

                 alias: unstar

    stars        npm stars [<user>]

    start        npm start [-- <args>]

    stop         npm stop [-- <args>]

    team         npm team create <scope:team>
                 npm team destroy <scope:team>
                 npm team add <scope:team> <user>
                 npm team rm <scope:team> <user>
                 npm team ls <scope>|<scope:team>
                 npm team edit <scope:team>

    test         npm test [-- <args>]

                 aliases: tst, t

    token        npm token list
                 npm token revoke <tokenKey>
                 npm token create [--read-only] [--cidr=list]


    uninstall    npm uninstall [<@scope>/]<pkg>[@<version>]... [--save-prod|--save-dev|--save-optional] [--no-save]

                 aliases: un, unlink, remove, rm, r

    unpublish    npm unpublish [<@scope>/]<pkg>[@<version>]

    update       npm update [-g] [<pkg>...]

                 aliases: up, upgrade, udpate

    version      npm version [<newversion> | major | minor | patch | premajor | preminor | prepatch | prerelease | from-git]
                 (run in package dir)
                 'npm -v' or 'npm --version' to print npm version (5.8.0)
                 'npm view <pkg> version' to view a package's published version
                 'npm ls' to inspect current package/dependency versions

    view         npm view [<@scope>/]<pkg>[@<version>] [<field>[.subfield]...]

                 aliases: v, info, show

    whoami       npm whoami [--registry <registry>]
                 (just prints username according to given registry)

npm <command> -h     quick help on <command>
npm -l           display full usage info
npm help <term>  search for help on <term>
npm help npm     involved overview

Specify configs in the ini-formatted file:
    C:\Users\Administrator\.npmrc
or on the command line via: npm <command> --key value
Config info can be viewed via: npm help config

npm@5.8.0 C:\Users\Administrator\AppData\Roaming\npm\node_modules\npm
```
* npm outdated

```
$ npm outdated
npm http request GET https://registry.npmjs.org/@luojianet%2fweb01
npm http request GET https://registry.npmjs.org/count_sheep
npm http request GET https://registry.npmjs.org/element-ui
npm http 200 https://registry.npmjs.org/count_sheep
npm http 200 https://registry.npmjs.org/element-ui
npm http 200 https://registry.npmjs.org/@luojianet%2fweb01
Package     Current  Wanted  Latest  Location
element-ui   1.4.13  1.4.13   2.3.3  npm
```
* npm dist-tag ls

```
[root@v430 28001]# npm dist-tag ls npm
3.x-latest: 3.10.9
3.x-next: 3.10.10
latest-1: 1.4.29
latest-2: 2.15.11
latest-3: 3.10.10
latest: 4.1.2
lts: 2.15.11
next-2: 2.15.11
next-3: 3.10.10
next: 4.2.0
v3.x-latest: 3.10.9
v3.x-next: 3.10.10
```
# 记录
* 全局安装路径：C:\Users\Administrator\AppData\Roaming\npm\node_modules
* npm update升级项目依赖
* npm update -g升级全局依赖
* "npm config ls -l" to show all defaults.
* 包路径https://www.npmjs.com/package/webpack
* meta数据https://registry.npmjs.org/webpack
* 个人中心https://www.npmjs.com/~
* npm login | npm adduser失败，是因为`npm config set registry https://registry.npm.taobao.org`,修改回官方链接就可以正常登录了
* npm view count_sheep dist,显示的下载地址会根据registry的配置不同而不同
* Interactively create a package.json file `npm init [-f|--force|-y|--yes]` This will ask you a bunch of questions, and then write a package.json for you.
* You can also set several config options for the init command. Some useful ones:
```
> npm set init.author.email "wombat@npmjs.com"
> npm set init.author.name "ag_dubs"
> npm set init.license "MIT"
```
* 命令npm view查看项目的metadata
* 命令npm view count_sheep time查看项目的更新时间轴
* 命令npm list --depth=0查看项目依赖的包
* 命令npm outdated --depth=0查看可更新的包
* npm <cmd> -h  quick help on <cmd>
* updating npm:npm install npm@latest -g
* npm -l display full usage info
* npm view   View registry info  aliases: info, show, v
* Patch releases: 补丁版本 
* Minor releases: 次版本
* Major releases: 主版本
```
Tags are a supplement to semver for organizing and labeling different versions of packages.
标签是语义化版本控制规范的补充，用于组织和标记不同版本的包。
Semantic Versioning Specification (SemVer)语义化版本控制规范
npm dist-tag ls
latest: 1.0.3
```
* npm unpublish [<@scope>/]<pkg>[@<version>]  Remove a package from the registry
```
To publish, you must have a user on the npm registry. If you don't have one, create it with npm adduser. If you created one on the site, use npm login to store the credentials on the client.
Use npm config ls to ensure that the credentials are stored on your client. Check that it has been added to the registry by going to https://npmjs.com/~.
npm version [<newversion> | major | minor | patch | premajor | preminor | prepatch | prerelease | from-git]
Run this in a package directory to bump the version and write the new data back to package.json and, if present, npm-shrinkwrap.json.
```
* npm install或npm update命令，从 registry 下载压缩包之后，都存放在本地的缓存目录。
```
npm 脚本的原理非常简单。每当执行npm run，就会自动新建一个 Shell，在这个 Shell 里面执行指定的脚本命令。因此，只要是 Shell（一般是 Bash）可以运行的命令，就可以写在 npm 脚本里面。
比较特别的是，npm run新建的这个 Shell，会将当前目录的node_modules/.bin子目录加入PATH变量，执行结束后，再将PATH变量恢复原样。
npm run pwd -- >pwd.txt
向 npm 脚本传入参数，要使用--标明。
如果是并行执行（即同时的平行执行），可以使用&符号。
npm run shram&npm run pwd
如果是继发执行（即只有前一个任务成功，才执行下一个任务），可以使用&&符号。
npm run shram && npm run pwd
这两个符号是 Bash 的功能。此外，还可以使用 node 的任务管理模块：script-runner、npm-run-all、redrun。
· "start": "node server.js": If there is a server.js file in the root of your package, then npm will default the start command to node server.js.
· "install": "node-gyp rebuild": If there is a binding.gyp file in the root of your package and you haven’t defined your own install or preinstall scripts, npm will default the install command to compile using node-gyp.
npm root [g]
Print the effective node_modules folder to stan-dard out.
tree -d node_modules
npm find-dupes
npm dedupe
https://www.npmjs.com/~johnqing
```
* 设置全局安装路径npm config set prefix C:\\Users\\Administrator\\AppData\\Roaming\\npm




