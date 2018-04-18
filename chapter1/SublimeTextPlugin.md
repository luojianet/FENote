# sublime官网
[sublime官网](http://www.sublimetext.com/)
# sublime插件官网
[packagecontrol](https://packagecontrol.io/)
# Installation - Package Control
## Simple
The simplest method of installation is through the Sublime Text console. The console is accessed via the ctrl+\` shortcut or the `View > Show Console` menu. Once open, paste the appropriate Python code for your version of Sublime Text into the console.
### Sublime Text 3
```Pathon
import urllib.request,os,hashlib; h = 'df21e130d211cfc94d9b0905775a7c0f' + '1e3d39e33b79698005270310898eea76'; pf = 'Package Control.sublime-package'; ipp = sublime.installed_packages_path(); urllib.request.install_opener( urllib.request.build_opener( urllib.request.ProxyHandler()) ); by = urllib.request.urlopen( 'http://packagecontrol.io/' + pf.replace(' ', '%20')).read(); dh = hashlib.sha256(by).hexdigest(); print('Error validating download (got %s instead of %s), please try manual install' % (dh, h)) if dh != h else open(os.path.join( ipp, pf), 'wb' ).write(by)
```
### Sublime Text 2
```Pathon
import urllib2,os,hashlib; h = 'df21e130d211cfc94d9b0905775a7c0f' + '1e3d39e33b79698005270310898eea76'; pf = 'Package Control.sublime-package'; ipp = sublime.installed_packages_path(); os.makedirs( ipp ) if not os.path.exists(ipp) else None; urllib2.install_opener( urllib2.build_opener( urllib2.ProxyHandler()) ); by = urllib2.urlopen( 'http://packagecontrol.io/' + pf.replace(' ', '%20')).read(); dh = hashlib.sha256(by).hexdigest(); open( os.path.join( ipp, pf), 'wb' ).write(by) if dh == h else None; print('Error validating download (got %s instead of %s), please try manual install' % (dh, h) if dh != h else 'Please restart Sublime Text to finish installation')
```
This code creates the Installed Packages folder for you (if necessary), and then downloads the `Package Control.sublime-package` into it. The download will be done over HTTP instead of HTTPS due to Python standard library limitations, however the file will be validated using SHA-256.
## Manual
If for some reason the console installation instructions do not work for you (such as having a proxy on your network), perform the following steps to manually install Package Control:
- Click the `Preferences > Browse Packages…` menu
- Browse up a folder and then into the `Installed Packages/` folder
- Download [Package Control.sublime-package](https://packagecontrol.io/Package%20Control.sublime-package) and copy it into the `Installed Packages/` directory
- Restart Sublime Text
# Using Package Control Installation 
- Install Package Control if you haven't yet.
- Use cmd+shift+P then Package Control: Install Package
- Look for Markdown Preview and install it.
# Manual Install
- Click the Preferences > Browse Packages… menu
- Browse up a folder and then into the Installed Packages/ folder
- Download ![zip package](https://github.com/revolunet/sublimetext-markdown-preview/archive/master.zip) rename it to Markdown Preview.sublime-package and copy it into the Installed Packages/ directory
- Restart Sublime Text
# Sublime Text 3 3126 注册码
```
—– BEGIN LICENSE —–  
TwitterInc  
200 User License  
EA7E-890007  
1D77F72E 390CDD93 4DCBA022 FAF60790  
61AA12C0 A37081C5 D0316412 4584D136  
94D7F7D4 95BC8C1C 527DA828 560BB037  
D1EDDD8C AE7B379F 50C9D69D B35179EF  
2FE898C4 8E4277A8 555CE714 E1FB0E43  
D5D52613 C3D12E98 BC49967F 7652EED2  
9D2D2E61 67610860 6D338B72 5CF95C69  
E36B85CC 84991F19 7575D828 470A92AB  
—— END LICENSE ——  
```
# 个性化设置Preferences->Settings
```
{
	"folder_exclude_patterns":
	[
		".svn",
		".git",
		".hg",
		"CVS",
		"node_modules",
		"bower_components"
	],
	"font_size": 12,
	"ignored_packages":
	[
		"Vintage"
	]
}
```
# Sublime 新技能
Show Unsaved Change
# Plugin
PackageControl

Alignment ctrl+alt+a

DocBlockr /**

Emmet

EmmetOneLine

HTMLBeautify
```
HTMLBeautify快捷键Ctrl+Alt+Shift+F
```

JsFormat
```
JsFormat快捷键Ctrl+Alt+F
```
SyncedSideBar

ConvertToUTF8

SFTP

```javascript
{
    "email": "xiaosong@xiaosong.me",
    "product_key": "d419f6-de89e9-0aae59-2acea1-07f92a"
}
```
ColorPicker ctrl+shift+c

AutoFileName

Vue Syntax Highlight
- 如果安装了插件代码还不高亮怎么办？
- 重启sublime打开vue代码
- view->syntax->Vue Component

[rem-unit](https://github.com/fisker/rem-unit)

参数配置文件：Sublime Text -> Preferences -> Package Settings -> rem-unit
- fontsize - html元素font-size值，默认为16。
- precision - px转rem的小数部分的最大长度，默认为8。
- leadingzero - 是否保留前导0，默认不保留。
- exts - 启用此插件的文件类型。默认为：[".css", ".scss", ".less", ".sass", ".styl"]。

Boxy Theme

![Boxy Theme](https://packagecontrol.io/readmes/img/4e79f9f88ec48b5d56092c9cfb451413d07da536.gif)

SublimeCodeIntel

BracketHighlighter

Markdown Preview


