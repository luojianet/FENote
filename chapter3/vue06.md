# v-if
在字符串模板中，比如 `Handlebars`，我们得像这样写一个条件块：
```
<!-- Handlebars 模板 -->
{{#if ok}}
  <h1>Yes</h1>
{{/if}}
```
在 Vue 中，我们使用 `v-if` 指令实现同样的功能：
```
<h1 v-if="ok">Yes</h1>
```
也可以用 `v-else` 添加一个“else 块”：
```
<h1 v-if="ok">Yes</h1>
<h1 v-else>No</h1>
```
## 在 `<template>` 元素上使用 `v-if` 条件渲染分组

因为 `v-if` 是一个指令，所以必须将它添加到一个元素上。但是如果想切换多个元素呢？此时可以把一个 `<template>` 元素当做不可见的包裹元素，并在上面使用 `v-if`。最终的渲染结果将不包含 `<template>` 元素。
```
<template v-if="ok">
  <h1>Title</h1>
  <p>Paragraph 1</p>
  <p>Paragraph 2</p>
</template>
```
## v-else
你可以使用 `v-else` 指令来表示 `v-if` 的“else 块”：
```
<div v-if="Math.random() > 0.5">
  Now you see me
</div>
<div v-else>
  Now you don't
</div>
```
`v-else` 元素必须紧跟在带 `v-if` 或者 `v-else-if` 的元素的后面，否则它将不会被识别。
