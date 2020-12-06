# API

MCBBS Loader 自身具有如下基本 API，在你的脚本中可以直接调用。

若无特别说明，所有代码均为 TypeScript 函数原型。

另请注意，`window` 可以省略。

## AjQuery

考虑到 MCBBS 内置的 jQuery 版本太老，这里有一个新的（3.5.1）：

```javascript
window.AjQuery.$
```

例如：

```javascript
window.AjQuery.$("body").html("你帖没了");
```

## AInfo

获取有关 API 的信息：

```javascript
window.AInfo.getAPIVersion():string
```

例如：

```javascript
console.log(window.AInfo.getAPIVersion());
// 0.9.4
```

## ADown

请求浏览器下载文件：

```javascript
window.ADown.downloadFile(url:string, name:string):void
```

例如：

```javascript
window.ADown.downloadFile("https://github.com/favicon.ico", "favicon.ico");
```

## AManager

模块管理器工具：

```javascript
window.AManager.require(url:string):void
// 请求装载模块，可以提供你依赖的模块的 URL。
window.AManager.openManager():void
// 在当前页面打开模块管理器
window.AManager.getAllModules():string[]
// 获取所有已经安装的模块
```

## AStorage

存储工具。

<div class="alert alert-warning"><i class="fa fa-exclamation-triangle"></i> 不要存储过大的数据，超出存储大小限制可能导致未知错误！</div>

```javascript
window.AStorage.storeData(tag:string, data:any):void
// 存储任何数据
window.AStorage.getData(tag:string, defaultVal:any):void
// 读取存储的数据
```

## ADep

模块导入导出工具。

```javascript
window.ADep.moduleExport(id:string, obj:any):void
// 导出以 id 标识的一个对象 obj，导入时 MCBBS Loader 将提供该对象
window.ADep.moduleImport(id:string, callback:(obj:any)=>void):void
// 以异步方式导入模块，获得的是导出时候的 obj 对象
// 这种方式有些类似 Node 的导入导出方式
```

例如：

```javascript
// 模块 1
// ...
ADep.moduleExport("mymodule", {a:5});
// ...

// 模块 2
// ...
ADep.moduleImport("mymodule", (obj)=>{
    console.log(obj.a);
    // 5
})
```

## AUtil

实用工具。

```javascript
window.AUtil.notification(text:string, title:string, image:string, callback:()=>void):void
// 发送 H5 通知
```

例如：

```javascript
Autil.notification("This is a message", "Hello World!", "https://www.mcbbs.net/favicon.ico", ()=>{
    alert("你点击了通知！")；
})
```

---

以上这些 API 当然是不够用的，但它们是构建辅助 API 所需要的所有原生 API。

你可以通过 `moduleExport` 来编写一些 API。