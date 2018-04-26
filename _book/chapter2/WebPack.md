# Study Webpack 4
Webpack is a bundler for javascript and friends. Packs many modules into a few bundled assets. Code Splitting allows to load parts for the application on demand. Through "loaders," modules can be CommonJs, AMD, ES6 modules, CSS, Images, JSON, Coffeescript, LESS, ... and your custom stuff. 
# 官网Learn List
* [Guides](https://webpack.js.org/guides/)
* [Installation](https://webpack.js.org/guides/installation/)
* [Getting Started](https://webpack.js.org/guides/getting-started/)
* [Asset Management](https://webpack.js.org/guides/asset-management/)
* [Output Management](https://webpack.js.org/guides/output-management/)
* [Development](https://webpack.js.org/guides/development/)
* [Hot Module Replacement](https://webpack.js.org/guides/hot-module-replacement/)
* [Tree Shaking](https://webpack.js.org/guides/tree-shaking/)
* [Production](https://webpack.js.org/guides/production/)
* [Code Splitting](https://webpack.js.org/guides/code-splitting/)

# 文章学习列表
* [使用 webpack 定制前端开发环境](https://juejin.im/book/5a6abad5518825733c144469)
```
基于 4.x 版本，从细节和深度上弄懂 webpack，随心所欲定制前端开发环境
teabyii 前支付宝前端开发，现唯品会高级开发
```
* [webpack 4.0.0-beta.0 新特性介绍](http://ju.outofmemory.cn/entry/343762)
* [webpack 4 发布了！](https://zhuanlan.zhihu.com/p/34028750)
* [splitChunksPlugin && runtimeChunkPlugin 配置杂记](https://www.cnblogs.com/ufex/p/8758792.html)
* [webpack实例](https://github.com/webpack/webpack/tree/master/examples)

# webpack打包形式
* webpack
* webpack src/index.js --output dist/bundle.js
* webpack --entry ./src/index.js --output dist/index.js
* webpack --config webpack.config.js
* node_modules/webpack/bin/webpack.js src/index.js --output dist/bundle.js
* npx webpack
* npx webpack src/index.js --output dist/bundle.js
* npm start
* npm run build
* npm run watch
* npm run development
* npm run production
* NODE_ENV=development npx webpack
* NODE_ENV=production npx webpack
# npx
* npx cowsay
```
$ npx cowsay "Hello Luojianet"
npx: 1 安装成功，用时 1.525 秒
Path must be a string. Received undefined
C:\github\webpack\node_modules\cowsay\cli.js
 _________________
< Hello Luojianet >
 -----------------
        \   ^__^
         \  (oo)\_______
            (__)\       )\/\
                ||----w |
                ||     ||
```
* npx http-server
```
$ npx http-server
npx: 1 安装成功，用时 1.637 秒
Path must be a string. Received undefined
npx: 23 安装成功，用时 4.008 秒
C:\Users\Administrator\AppData\Roaming\npm-cache\_npx\9732\node_modules\http-server\bin\http-server
Starting up http-server, serving ./
Available on:
  http://192.168.33.97:8080
  http://192.168.56.1:8080
  http://127.0.0.1:8080
Hit CTRL-C to stop the server
```
# npm list
* npm list --depth=0
```
$ npm list --depth=0
webpack-demo4@1.0.0 C:\Git\webpack\AssetManagement
+-- css-loader@0.28.11
+-- lodash@4.17.5
+-- style-loader@0.20.3
+-- webpack@4.4.1
`-- webpack-cli@2.0.13
```
* npm list -g --depth=0
```
$ npm list -g --depth=0
C:\Users\Administrator\AppData\Roaming\npm
+-- vue-cli@2.9.1
+-- webpack@4.4.1
`-- webpack-cli@2.0.13
```
*  npm list --depth=0 (**记录**：`UNMET PEER DEPENDENCY webpack@4.4.1`未满足的对等的依赖 )

```
$ npm list --depth=0 
webpack-demo4@1.0.0 C:\github\webpack\AssetManagement
+-- css-loader@0.28.11
+-- extract-text-webpack-plugin@3.0.2
+-- lodash@4.17.5
+-- style-loader@0.20.3
+-- UNMET PEER DEPENDENCY webpack@4.4.1
`-- webpack-cli@2.0.13

npm ERR! peer dep missing: webpack@^3.1.0, required by extract-text-webpack-plugin@3.0.2
npm ERR! peer dep missing: ajv@^6.0.0, required by ajv-keywords@3.1.0
```
# webpack.config.js文件module字段的4种写法
```
var obj = {
    module_1: { //多模块不需要配置
        rules: [{
            test: /\.css$/,
            use: ["style-loader", "css-loader"]
        }]
    },
    module_2: { //单模块需要配置
        rules: [{
            test: /\.css$/,
            loader: "css-loader",
            options: {
                minimize: true,
                sourceMap: true
            }
        }]
    },
    module_3: { //多模块需要配置
        rules: [{
            test: /\.css$/,
            use: [{
                loader: "style-loader",
                options: {
                    attrs: {
                        title: "gogo",
                        class: "styleForSelector"
                    },
                    insertAt: {
                        before: '#title'
                    }, //'top', 'bottom', or Object.
                    singleton: true
                }
            }, {
                loader: "css-loader",
                options: {
                    minimize: false,
                    sourceMap: true
                }
            }]
        }]
    },
    module_4: { //多模块需要配置
        rules: [{
            test: /\.css$/,
            use: [
                "style-loader",
                {
                    loader: "css-loader",
                    options: {
                        minimize: true
                    }
                }
            ]
        }]
    }
}
```
# NODE_ENV=production 环境变量设置
* shell
```
NODE_ENV=development node app.js
```
* shell
```
npx webpack --config webpack.common.js --define process.env.NODE_ENV="'production'"
```
* cmd
```	
C:\Users\Administrator>set NODE_ENV=development
C:\Users\Administrator>node
> process.env.NODE_ENV
'development'
```
* cmd
```
set NODE_ENV=development && node env.js
set NODE_ENV=production && node env.js
```
* npm scripts
```
"scripts": {
	"buildNoPostcssProperty": "postcss css/style.css --use autoprefixer --output dist/style.css --no-map",
	"build": "postcss css/transition.css --output dist/transition.css --no-map",
	"development": "set NODE_ENV=development&& node env.js",
	"production": "set NODE_ENV=production&& node env.js",
	"start": "cross-env NODE_ENV=development node env.js"
}
//set NODE_ENV=development,&&符号前面不可以有空格
```
* cross-env
```
npm install --save-dev cross-env
"scripts":{
	"start": "cross-env NODE_ENV=development node env.js"
}
`
```
* webpack.config.js
```
new webpack.DefinePlugin({
  'process.env.NODE_ENV': JSON.stringify('production')
})
```        

# webpack参数列表
<details>
<summary>webpack-cli 2.0.14</summary>
```
$ npx webpack --help
npx: installed 1 in 2.868s
Path must be a string. Received undefined
C:\html\www.yanhu.com\201804\20180404\node_modules\webpack\bin\webpack.js
webpack-cli 2.0.14

Usage: webpack-cli [options]
       webpack-cli [options] --entry <entry> --output <output>
       webpack-cli [options] <entries...> --output <output>

For more information, see https://webpack.js.org/api/cli/.

Initialization:
  --init             Initializes a new webpack configuration or loads a
                     addon if specified                                [boolean]
  --migrate          Migrate your webpack configuration from webpack 1 to
                     webpack 2                                         [boolean]
  --add              Adds a webpack component to your configuration file
                                                                       [boolean]
  --generate-loader  Generates a new webpack loader project            [boolean]
  --generate-plugin  Generates a new webpack plugin project            [boolean]

Config options:
  --config               Path to the config file
                         [string] [default: webpack.config.js or webpackfile.js]
  --config-register, -r  Preload one or more modules before loading the webpack
                         configuration      [array] [default: module id or path]
  --config-name          Name of the config to use                      [string]
  --env                  Environment passed to the config, when it is a function
  --mode                 Mode to use
                                 [string] [choices: "development", "production"]

Basic options:
  --context    The root directory for resolving entry point and stats
                                       [string] [default: The current directory]
  --entry      The entry point                                          [string]
  --watch, -w  Watch the filesystem for changes                        [boolean]
  --debug      Switch loaders to debug mode                            [boolean]
  --devtool    Enable devtool for better debugging experience (Example:
               --devtool eval-cheap-module-source-map)                  [string]
  -d           shortcut for --debug --devtool eval-cheap-module-source-map
               --output-pathinfo                                       [boolean]
  -p           shortcut for --optimize-minimize --define
               process.env.NODE_ENV="production"                       [boolean]
  --progress   Print compilation progress in percentage                [boolean]

Module options:
  --module-bind       Bind an extension to a loader                     [string]
  --module-bind-post  Bind an extension to a post loader                [string]
  --module-bind-pre   Bind an extension to a pre loader                 [string]

Output options:
  --output, -o                  The output path and file for compilation assets
  --output-path                 The output path for compilation assets
                                       [string] [default: The current directory]
  --output-filename             The output filename of the bundle
                                                   [string] [default: [name].js]
  --output-chunk-filename       The output filename for additional chunks
       [string] [default: filename with [id] instead of [name] or [id] prefixed]
  --output-source-map-filename  The output filename for the SourceMap   [string]
  --output-public-path          The public path for the assets          [string]
  --output-jsonp-function       The name of the jsonp function used for chunk
                                loading                                 [string]
  --output-pathinfo             Include a comment with the request for every
                                dependency (require, import, etc.)     [boolean]
  --output-library              Expose the exports of the entry point as library
                                                                        [string]
  --output-library-target       The type for exposing the exports of the entry
                                point as library                        [string]

Advanced options:
  --records-input-path       Path to the records file (reading)         [string]
  --records-output-path      Path to the records file (writing)         [string]
  --records-path             Path to the records file                   [string]
  --define                   Define any free var in the bundle          [string]
  --target                   The targeted execution environment         [string]
  --cache                    Enable in memory caching
                      [boolean] [default: It's enabled by default when watching]
  --watch-stdin, --stdin     Exit the process when stdin is closed     [boolean]
  --watch-aggregate-timeout  Timeout for gathering changes while watching
  --watch-poll               The polling interval for watching (also enable
                             polling)                                   [string]
  --hot                      Enables Hot Module Replacement            [boolean]
  --prefetch                 Prefetch this request (Example: --prefetch
                             ./file.js)                                 [string]
  --provide                  Provide these modules as free vars in all modules
                             (Example: --provide jQuery=jquery)         [string]
  --labeled-modules          Enables labeled modules                   [boolean]
  --plugin                   Load this plugin                           [string]
  --bail                     Abort the compilation on first error
                                                       [boolean] [default: null]
  --profile                  Profile the compilation and include information in
                             stats                     [boolean] [default: null]

Resolving options:
  --resolve-alias         Setup a module alias for resolving (Example:
                          jquery-plugin=jquery.plugin)                  [string]
  --resolve-extensions    Setup extensions that should be used to resolve
                          modules (Example: --resolve-extensions .es6,.js)
                                                                         [array]
  --resolve-loader-alias  Setup a loader alias for resolving            [string]

Optimizing options:
  --optimize-max-chunks      Try to keep the chunk count below a limit
  --optimize-min-chunk-size  Try to keep the chunk size above a limit
  --optimize-minimize        Minimize javascript and switches loaders to
                             minimizing                                [boolean]

Stats options:
  --color, --colors               Enables/Disables colors on the console
                                           [boolean] [default: (supports-color)]
  --sort-modules-by               Sorts the modules list by property in module
                                                                        [string]
  --sort-chunks-by                Sorts the chunks list by property in chunk
                                                                        [string]
  --sort-assets-by                Sorts the assets list by property in asset
                                                                        [string]
  --hide-modules                  Hides info about modules             [boolean]
  --display-exclude               Exclude modules in the output         [string]
  --display-modules               Display even excluded modules in the output
                                                                       [boolean]
  --display-max-modules           Sets the maximum number of visible modules in
                                  output                                [number]
  --display-chunks                Display chunks in the output         [boolean]
  --display-entrypoints           Display entry points in the output   [boolean]
  --display-origins               Display origins of chunks in the output
                                                                       [boolean]
  --display-cached                Display also cached modules in the output
                                                                       [boolean]
  --display-cached-assets         Display also cached assets in the output
                                                                       [boolean]
  --display-reasons               Display reasons about module inclusion in the
                                  output                               [boolean]
  --display-depth                 Display distance from entry point for each
                                  module                               [boolean]
  --display-used-exports          Display information about used exports in
                                  modules (Tree Shaking)               [boolean]
  --display-provided-exports      Display information about exports provided
                                  from modules                         [boolean]
  --display-optimization-bailout  Display information about why optimization
                                  bailed out for modules               [boolean]
  --display-error-details         Display details about errors         [boolean]
  --display                       Select display preset
              [string] [choices: "", "verbose", "detailed", "normal", "minimal",
                                                          "errors-only", "none"]
  --verbose                       Show more details                    [boolean]
  --info-verbosity                Controls the output of lifecycle messaging
                                  e.g. Started watching files...
                 [string] [choices: "none", "info", "verbose"] [default: "info"]
  --build-delimiter               Display custom text after build output[string]

Options:
  --help, -h     Show help                                             [boolean]
  --version, -v  Show version number                                   [boolean]
  --silent       Prevent output from being displayed in stdout         [boolean]
  --json, -j     Prints the result as JSON.                            [boolean]
```
</details>
# webpack常用参数
* --help
* --version
* --progress 
* --module-bind 'txt=raw-loader'
* --devtool inline-cheap-source-map
* --display-modules 
* --mode=production
* --color
* --watch
* --verbose
* --json > stats.json
* --env.production    # 设置 env.production == true
* --env.platform=web  # 设置 env.platform == "web"

# 学习webpack 4依赖模块列表
```
"devDependencies": {
  "webpack": "^4.2.0",
  "webpack-cli": "^2.0.12",
  "webpack-dev-server": "^3.1.3",
  "webpack-merge": "^4.1.2",
  "style-loader": "^0.20.3",
  "css-loader": "^0.28.11",
  "url-loader": "^1.0.1",
  "file-loader": "^1.1.11",
  "raw-loader": "^0.5.1",
  "xml-loader": "^1.2.1",
  "cross-env": "^5.1.4",
  "postcss-loader": "^2.1.3",
  "autoprefixer": "^8.2.0",
  "extract-text-webpack-plugin": "^4.0.0-beta.0",
  "html-webpack-plugin": "^3.2.0",
  "html-webpack-template": "^6.2.0",
  "clean-webpack-plugin": "^0.1.19",
  "babel-core": "^6.26.0",
  "babel-loader": "^7.1.4",
  "babel-plugin-add-module-exports": "^0.2.1",
  "babel-plugin-transform-es2015-modules-commonjs": "^6.26.0",
  "babel-plugin-transform-es3-member-expression-literals": "^6.22.0",
  "babel-plugin-transform-es3-property-literals": "^6.22.0",
  "babel-preset-env": "^1.6.1",
  "nodemon": "^1.17.3",
  "uglifyjs-webpack-plugin": "^1.2.4"
},
"dependencies": {
  "bluebird": "^3.5.1",
  "console-polyfill": "^0.3.0",
  "es5-shim": "^4.5.10",
  "jquery": "^1.12.4",
  "underscore": "^1.8.3",
  "zepto": "^1.2.0",
  "promise-polyfill": "^7.1.2"
}
```
# 笔记
* node httpServer.js webpack-demo/ 可以对具体目录启动静态服务器
* npx http-server webpack-demo/ 可以对具体目录启动静态服务器
* We also need to adjust our package.json file in order to make sure we mark our package as private, as well as removing the main entry. This is to prevent an accidental publish of your code.
* 项目代码依赖npm install --save，项目开发工具配置文件依赖npm insatll --save-dev
* When installing a package that will be bundled into your production bundle, you should use `npm install --save`. If you're installing a package for development purposes (e.g. a linter, testing libraries, etc.) then you should use `npm install --save-dev`.
* Webpack is used to compile JavaScript modules.Webpack is A bundler for javascript.
* To run the local installation of webpack you can access its bin version as `node_modules/.bin/webpack`
* 不推荐全局安装 webpack。这会将你项目中的 webpack 锁定到指定版本，并且在使用不同的 webpack 版本的项目中，可能会导致构建失败。
* Note that this is `not a recommended practice`. Installing globally locks you down to a specific version of webpack and could fail in projects that use a different version.
* [webpack打包形式](#webpack打包形式)前四个需要全局安装`webpack`，`webpack-cli`.
* Loaders can be chained by passing multiple loaders, which will be applied from right to left (last to first configured).
* WARNING in configuration:The 'mode' option has not been set. Set 'mode' option to 'development' or 'production' to enable defaults for this environment.You can also set it to 'none' to disable any default behavior. Learn more: https://webpack.js.org
* Note that webpack will not alter any code other than `import` and `export` statements. If you are using other ES2015 features, make sure to use a transpiler such as Babel or Bublé via webpack's loader system.
* If a `webpack.config.js` is present, the `webpack` command picks it up by default. We use the `--config` option here only to show that you can pass a config of any name. This will be useful for more complex configurations that need to be split into multiple files.
* 如果webpack.config.js存在，则该webpack命令默认采用它。我们在--config这里使用这个选项只是为了表明你可以传递任何名字的配置。这对于需要拆分为多个文件的更复杂的配置很有用。
* 通过向 `npm run build` 命令和你的参数之间添加两个中横线，可以将自定义参数传递给 webpack，例如：`npm run build -- --colors`。
* 如果你使用的是 npm 5，你可能还会在目录中看到一个 package-lock.json 文件。
* 你可以指示 webpack "watch" 依赖图中的所有文件以进行更改。如果其中一个文件被更新，代码将被重新编译，所以你不必手动运行整个构建。我们添加一个用于启动 webpack 的观察模式的 npm script 脚本：`"watch": "webpack --watch --color"`。
* Simple rule: one entry point per HTML page. SPA: one entry point, MPA: multiple entry points.
* You can specify an entry point (or multiple entry points) by configuring the `entry` property in the webpack configuration. It defaults to `./src`.
* loader属性的等价写法
```
{
    test: /\.jpeg$/,
    use: [{
        loader: 'url-loader',
        options: {
            limit: '1024'
        }
    }, ]
}
```

```
{
    test: /\.jpeg$/,
    use: 'url-loader?limit=1024
}
```
* webpack.config.js commonJS模块化写法

```
const path = require('path');

const config = {
  entry: './path/to/my/entry/file.js',
  output: {
    path: path.resolve(__dirname, 'dist'),
    filename: 'my-first-webpack.bundle.js'
  },
  module: {
    rules: [
      { test: /\.txt$/, use: 'raw-loader' }
    ]
  }
};

module.exports = config;
```

* In order to use a plugin, you need to `require()` it and add it to the `plugins` array. Most plugins are customizable through options. Since you can use a plugin multiple times in a config for different purposes, you need to create an instance of it by calling it with the `new` operator.

```
const HtmlWebpackPlugin = require('html-webpack-plugin'); //installed via npm
const webpack = require('webpack'); //to access built-in plugins

const config = {
  module: {
    rules: [
      { test: /\.txt$/, use: 'raw-loader' }
    ]
  },
  plugins: [
    new webpack.optimize.UglifyJsPlugin(),
    new HtmlWebpackPlugin({template: './src/index.html'})
  ]
};

module.exports = config;
```
* The single `entry` syntax for the entry property is a shorthand for:
```
const config = {
  entry: {
    main: './path/to/my/entry/file.js'
  }
};
```
* Configuring the `output` configuration options tells webpack how to write the compiled files to disk. Note that, while there can be multiple `entry` points, only one `output` configuration is specified.
* If your configuration creates more than a single "chunk" (as with multiple entry points or when using plugins like CommonsChunkPlugin), you should use substitutions to ensure that each file has a unique name.
* Please remember that setting `NODE_ENV` doesn't automatically set `mode`.
* Mode: development's mains

```webpack.config.js
// webpack.development.config.js
module.exports = {
+ mode: 'development'
- plugins: [
-   new webpack.NamedModulesPlugin(),
-   new webpack.DefinePlugin({ "process.env.NODE_ENV": JSON.stringify("development") }),
- ]
}
```

* Mode: production's mains

```
// webpack.production.config.js
module.exports = {
+  mode: 'production',
-  plugins: [
-    new UglifyJsPlugin(/* ... */),
-    new webpack.DefinePlugin({ "process.env.NODE_ENV": JSON.stringify("production") }),
-    new webpack.optimize.ModuleConcatenationPlugin(),
-    new webpack.NoEmitOnErrorsPlugin()
-  ]
}
```

* Using Loaders

	There are three ways to use loaders in your application:

	* **Configuration** (recommended): Specify them in your webpack.config.js file.
	* **Inline**: Specify them explicitly in each import statement.
	* **CLI**: Specify them within a shell command.
* It's possible to specify loaders in an `import` statement.Separate loaders from the resource with `!`. Each part is resolved relative to the current directory.
* Options can be passed with a query parameter, e.g. `?key=value&foo=bar`, or a JSON object, e.g. `?{"key":"value","foo":"bar"}`.
* Since **plugins** can take arguments/options, you must pass a `new` instance to the `plugins` property in your webpack configuration.
* Support for JSON is actually built-in.
* 验证webpack 4引入commonJS、AMD模块后IE8的兼容性[demo](https://github.com/luojianet/webpack/tree/master/WebpackModule),研究打包后的代码，了解webpack是怎么处理commonJS、AMD模块局部作用域的？入口文件是如何调用被引入模块的内部函数的？。然后再引入ES模块，对比下webpack针对3种模块分别所做的处理。
* 未解决的问题：How can I keep the css order in the css file when I use extract-text-webpack-plugin？[link1](https://github.com/webpack-contrib/extract-text-webpack-plugin/issues/200),[link2](https://github.com/webpack-contrib/extract-text-webpack-plugin/issues/165),[link3](https://github.com/webpack/webpack/issues/215),[link4](https://github.com/symfony/webpack-encore/issues/292)
* set NODE_ENV=development,&&符号前面不可以有空格
* `nodemon`用来监听`webpack.config.js`文件的状态，只要发生改变，就重新执行命令。`--watch`用来监听一个或者多个文件，`--exec`是nodemon用来执行其它的命令。[配置](https://c9.io/remy/nodemon )
* 模块解析，相对路径情况下，使用 import 或 require 的资源文件(resource file)所在的目录被认为是上下文目录(context directory)。在 import/require 中给定的相对路径，会添加此上下文路径(context path)，以产生模块的绝对路径(absolute path)。
* 作为导出一个配置对象的替代，还有一种可选的导出方式是，从 webpack 配置文件中导出一个函数。该函数在调用时，可传入两个参数：环境对象(environment)作为第一个参数。有关语法示例，请查看CLI 文档的[环境选项](https://webpack.js.org/api/cli/#environment-options)。 一个选项 map 对象（argv）作为第二个参数。
* 对于单个入口起点，filename 会是一个静态名称。当通过多个入口起点(entry point)、代码拆分(code splitting)或各种插件(plugin)创建多个 bundle，应该使用以下一种替换方式，来赋予每个 bundle 一个唯一的名称[name][id][hash][chunkhash][query]
* modules[moduleId].call，它会传入新初始化的 module.exports 来作为模块闭包的上下文（context）,对于 Zepto 来说，它初始化时使用的 this其实就是 module.exports，但这个 module.exports 没有赋值过任何变量，即 Zepto 初始化使用的 this 为空对象。
* `output.sourceMapFilename`This option is only used when `devtool` uses a `source-map` option which writes an output file.
* `uglifyjs-webpack-plugin`使用这个插件生成sourcemap，只有设置devtool:source-map的时候才生效
* sourcemap只在打开开发调试工具时才启用，普通的访问不会导致下载.map文件。
* 在使用 `uglifyjs-webpack-plugin` 时，你必须提供 `sourceMap：true` 选项来启用 source map 支持。
* 任何位于 `/src` 的本地代码都可以关联到 process.env.NODE_ENV 环境变量
* 和以上描述的 `DefinePlugin` 实例相同，`--define process.env.NODE_ENV="'production'"`也会做同样的事情。并且，`webpack -p` 将自动地调用上述这些标记，从而调用需要引入的插件。`webpack -d`
* `-d` 含义`--debug --devtool cheap-module-eval-source-map --output-pathinfo`
* `-p` 含义`--optimize-minimize --define process.env.NODE_ENV="production"`