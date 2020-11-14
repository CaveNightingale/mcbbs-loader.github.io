# 元信息

元信息决定了 MCBBS Loader 如何显示你的模块。

元信息支持任何键值对，键不能有空格。

用 `// @键 值` 即可定义元信息。

元信息的第一行必须是 `// MCBBS-Module`，最后一行必须是 `// -MCBBS-Module`，其它信息一行一个夹在中间。

目前 MCBBS Loader 只识别如下元信息（所有其它的信息仍旧被存储，但不使用）：

## id

必填项，模块唯一识别 ID，建议用包名命名。

示例：

```javascript
// @id com.example.examplemodule
```

## icon

可选项，指定图标，可以使用图片 URL 或者 BASE64 编码。

示例：

```javascript
// @icon https://github.com/favicon.ico
// @icon data:image/png;base64,/9j/4AAQSk（后略）
```

## description

一段简短的描述，可以使用 HTML。

示例：

```javascript
// @description 一个<b>加粗</b>的模块。
```

## name

模块的名字，可以使用 HTML。

## author

作者的名字，可以使用 HTML。

## version

版本号，更新时使用，只能使用**数字**和**点**表示。

只有版本号没有用，它需要和 `@update` 一起使用。

示例：

```javascript
// @version 12
// @version 5.9.23
// @version 233.344.455.566.677
```

## update

更新 URL，每次脚本加载时会检查一次更新，该 URL 应该指向新的脚本的位置。你可以每次固定将脚本发布到同一个位置。

示例：

```javascript
// @update https://cdn.jsdelivr.net/gh/MCBBS-Loader/MCBBS-RunJS@main/main.js
```

<div class="alert alert-warning"><i class="fa fa-exclamation-triangle"></i> <b>不要</b>使用 jsDelivr 的压缩服务，它会移除元信息！</div>

---

目前只有这些元信息被识别，未来可能会有更多的信息。