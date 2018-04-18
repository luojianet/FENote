# Introduction
gitbook 的基本用法非常简单，基本上就只有两步：

1.使用 `gitbook init` 初始化书籍目录
2.使用 `gitbook serve` 编译书籍
# CLI
* gitbook serve
```
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
info: >> generation finished with success in 0.6s !

Starting server ...
Serving book on http://localhost:4000
```
`gitbook serve` 命令实际上会首先调用 `gitbook build` 编译书籍，完成以后会打开一个 web 服务器，监听在本地的 4000 端口。