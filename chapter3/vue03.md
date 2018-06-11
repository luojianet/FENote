# 插值
## 文本
数据绑定最常见的形式就是使用“Mustache”语法 (双大括号) 的文本插值：
```
<span>Message: {{ msg }}</span>
```
Mustache 标签将会被替代为对应数据对象上 `msg` 属性的值。无论何时，绑定的数据对象上 `msg` 属性发生了改变，插值处的内容都会更新。

通过使用 [v-once 指令](https://cn.vuejs.org/v2/api/#v-once)，你也能执行一次性地插值，当数据改变时，插值处的内容不会更新。但请留心这会影响到该节点上的其它数据绑定：
```
<span v-once>这个将不会改变: {{ msg }}</span>
```
## 原始 HTML
双大括号会将数据解释为普通文本，而非 HTML 代码。为了输出真正的 HTML，你需要使用 `v-html` 指令：
```
<p>Using mustaches: {{ rawHtml }}</p>
<p>Using v-html directive: <span v-html="rawHtml"></span></p>
```
你的站点上动态渲染的任意 HTML 可能会非常危险，因为它很容易导致 [XSS 攻击](https://en.wikipedia.org/wiki/Cross-site_scripting)。请只对可信内容使用 HTML 插值，绝不要对用户提供的内容使用插值。
## 特性
Mustache 语法不能作用在 HTML 特性上，遇到这种情况应该使用 [v-bind 指令](https://cn.vuejs.org/v2/api/#v-bind)：
```
<div v-bind:id="dynamicId"></div>
```


