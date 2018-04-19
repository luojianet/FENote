# Introduction
gitbook 的基本用法非常简单，基本上就只有两步：

1. 使用 `gitbook init` 初始化书籍目录
2. 使用 `gitbook serve` 编译书籍

# Study List
* [GitBook 简明教程](http://www.chengweiyang.cn/gitbook/)
* [git serve can't restart when file changes](https://github.com/GitbookIO/gitbook/issues/1379)
# CLI
* gitbook serve

`gitbook serve` 命令实际上会首先调用 `gitbook build` 编译书籍，完成以后会打开一个 web 服务器，监听在本地的 4000 端口。
```shell
$ gitbook serve
Live reload server started on port: 35729
Press CTRL+C to quit ...

info: 7 plugins are installed
info: loading plugin "livereload"... OK
info: loading plugin "highlight"... OK
info: loading plugin "search"... OK
info: loading plugin "lunr"... OK
info: loading plugin "sharing"... OK
info: loading plugin "fontsettings"... OK
info: loading plugin "theme-default"... OK
info: found 3 pages
info: found 2 asset files
info: generation finished with success in 0.6s !

Starting server ...
Serving book on http://localhost:4000
```


* nslookup febook.xuliehaonet.com

```shell
服务器:  UnKnown
Address:  192.168.8.24

非权威应答:
名称:    cdn.gitbook.com
Address:  128.199.232.1
Aliases:  febook.xuliehaonet.com
          www.gitbooks.io
```

* gitbook serve [issues](https://github.com/GitbookIO/gitbook/issues/1379#issuecomment-320579569)

I built `gitbook serve` success, but when I change file the gitbook serve restart fail.Here is the error message.

Here's a solution

1. `gitbook serve`
2. delete _book folder `once`
3. now each time you change the md file, the server will stop and start over again and again

```shell
Starting server ...
Serving book on http://localhost:4000
Restart after change in file SUMMARY.md

Stopping server
events.js:141
      throw er; // Unhandled 'error' event
      ^

Error: EPERM: operation not permitted, lstat 'G:\gitbook-touchevent\_book'
    at Error (native)
node version:4.4.2
gitook version: 2.2.0
```
# 笔记
* 配置host加速访问`139.59.16.50 febook.xuliehaonet.com`