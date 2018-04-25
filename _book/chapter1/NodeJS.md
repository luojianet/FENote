# NodeJS httpServer.js
* [仓库地址](https://github.com/luojianet/NodeJS)
* 企业网站演示：`node httpServer.js 2018/201803/20180308/20141202001`

# 模块包装器
在执行模块代码之前，Node.js 会使用一个如下的[函数包装器](http://nodejs.cn/api/modules.html#modules_the_module_wrapper)将其包装：
```js
(function(exports, require, module, __filename, __dirname) {
// 模块的代码实际上在这里
});
```
通过这样做，Node.js 实现了以下几点：
* 它保持了顶层的变量（用 `var`、`const` 或 `let` 定义）作用在模块范围内，而不是全局对象。
* 它有助于提供一些看似全局的但实际上是模块特定的变量，例如：
	* 实现者可以用于从模块中导出值的 `module` 和 `exports` 对象。
	* 包含模块绝对文件名和目录路径的快捷变量 `__filename` 和 `__dirname` 。

# 学习列表
* [廖雪峰NodeJS教程](https://www.liaoxuefeng.com/wiki/001434446689867b27157e896e74d51a89c25cc8b43bdb3000/00143450141843488beddae2a1044cab5acb5125baf0882000)
* [API 文档 | Node.js 中文网](http://nodejs.cn/api/)
* [path | Node.js API 文档](http://nodejs.cn/api/path.html)
* [module | Node.js API 文档](http://nodejs.cn/api/modules.html)
* [字符串的扩展 - ECMAScript 6入门](http://es6.ruanyifeng.com/#docs/string)
* [函数的扩展 - ECMAScript 6入门](http://es6.ruanyifeng.com/#docs/function#%E7%AE%AD%E5%A4%B4%E5%87%BD%E6%95%B0)
* [对象的扩展 - ECMAScript 6入门](http://es6.ruanyifeng.com/#docs/object)
* [async 函数 - ECMAScript 6入门](http://es6.ruanyifeng.com/#docs/async)
* [Promise 对象 - ECMAScript 6入门](http://es6.ruanyifeng.com/#docs/promise)
* [Module 的语法 - ECMAScript 6入门](http://es6.ruanyifeng.com/#docs/module)

# 笔记
* ES6模块的设计思想，是尽量的静态化，使得编译时就能确定模块的依赖关系，以及输入和输出的变量。CommonJS和AMD模块，都只能在运行时确定这些东西。 

# 待解决问题
* 旧版本mime.lookup(pathname)
* 新版本mime.getType(pathname)
* 有时间了看mime官方变更说明，什么时候lookup方法换成了getType方法，并且还不向下兼容
