# 元信息

元信息决定了 MCBBS Loader 如何显示你的模块。

元信息支持任何键值对，键不能有空格。

如果需要跨行书写元信息，需要在行末添加反斜杠`\`。

用 `<键>=<值>` 即可定义元信息。
等号前后可以有空格。

元信息的第一行必须是 `/* MCBBS Module`，最后一行必须是 `*/`，其它信息一行一个夹在中间。

目前 MCBBS Loader 只识别如下元信息（所有其它的信息仍旧被存储，但不使用）：

## id

必填项，模块唯一识别 ID，建议用包名命名，参考杂项篇目。

示例：

```properties
id=com.example.examplemodule
```

## icon

指定图标，填写 URL 。

示例：

```properties
icon=https://github.com/favicon.ico
icon=data:image/png;base64,/9j/4AAQSk（后略）
```

## description

一段简短的描述，可以使用 HTML。

示例：

```properties
description=一个<b>加粗</b>的模块。
```

## name

模块的名字，可以使用 HTML。

## author

作者的名字，可以使用 HTML。

## version

版本号，更新时使用，只能使用**数字**和**点**表示。

只有版本号没有用，它需要和 `updateURL` 一起使用。

示例：

```properties
version=12
version=5.9.23
version=233.344.455.566.677
```

## updateURL

更新 URL，每次脚本加载时会检查一次更新，该 URL 应该指向新的脚本的位置。你可以每次固定将脚本发布到同一个位置。

示例：

```properties
updateURL=https://cdn.jsdelivr.net/gh/MCBBS-Loader/MCBBS-RunJS@main/main.js
```

<div class="alert alert-warning"><i class="fa fa-exclamation-triangle"></i> <b>不要</b>使用 jsDelivr 的压缩服务，它会移除元信息！</div>

## depend

检查依赖关系，可以指定多个依赖项，中间用英文逗号分割，如果依赖项未安装或者未启用，则只能保证与依赖关系无关的模块加载。

指定依赖项的时候，可以使用模块的ID或者GID，使用GID时，安装时会自动安装依赖模块。

<span style="color: brown">**情况有变：我们强烈建议不要使用GID指定依赖项，因为关于GID的支持由于严重缺陷在洞穴夜莺的分支上被回退，这个操作不久后将被合并入主分支，目前洞穴夜莺分支使用`<依赖项>[ -> <下载地址/GID>]`的方式指定依赖。**</span>

## before

拥有此属性的脚本会在所有指定的脚本之前运行，如果指定的脚本未安装将被**忽略**，如果没有任何符合要求的加载顺序解法，只能保证和问题模块完全无关的模块<sup>[1]</sup>能够加载。

## after

和before基本一样，但是脚本会在指定项之后加载。

## permissions

特殊权限列表
目前只有loader:core被支持，它用于加载需要高权限的脚本。将来会有更多权限支持。

目前只有这些元信息被识别，未来可能会有更多的信息。

---
1) 与出问题的脚本没有直接或者间接的通过after、before、depend上的联系，有些模块即使与问题模块有关也能加载，但是不作保证。