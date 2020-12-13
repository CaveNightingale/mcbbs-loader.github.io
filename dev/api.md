# API

MCBBS Loader 自身具有如下基本 API，在你的脚本中可以直接调用。

若无特别说明，所有代码均为 TypeScript 函数原型。

`MCBBS`变量是一个插入在模块头部声明的局部变量，不同的模块所持有的`MCBBS`对象不同，其结构如下：  
- `MCBBS`
  - `$(selector, context)`  
    jQuery实例  
  - `closeStatus(move)`  
    关闭底部提示  
    - move - 动画持续的时间  
    - 无返回值
  - `constructor(id)`  
    MCBBSAPI类  
    - id - 命名空间  
  - `createConfig(stgid, name, type, desc)`  
    创建配置项  
    - stgid - 一个存储id  
    - name - 在设置页面显示的名字  
    - type - 类型，可以为`'checkbox'`代表复选框，或者任何其他内容代表文本框  
    - desc - 描述，在设置界面的描述  
    - 无返回值
  - `download(url, name)`  
    不经过用户确认下载文件  
    - url - 欲下载的地址  
    - name - 保存的文件名  
    - 无返回值  
  - `eval(script)`  
    以GM权限执行脚本  
    需要`loader:core`权限才能访问  
    - script - 欲运行的表达式
    - 返回一个Promise代表运行结果
  - `export_(idIn, obj)`  
    导出一个对象  
    - idIn - 导出id  
    - obj - 导出对象  
    - 无返回值  
  - `getAPIVersion()`  
    获取API版本  
    - 返回当前版本的数值
  - `getConfigVal(idIn[, dval])`  
    获取配置选项的值  
    - idIn - 存储id  
    - dval - 默认值  
    - 返回当前配置选项的值，若没有则默认值  
  - `getData(k[, dv])`  
    获取存储的内容
    - k - 存储id
    - dv - 默认值  
    - 返回当前存储的值，若没有则默认值  
  - `id`  
    当前API的命名空间，和权限检查有关  
  - `import_(id, callback)`  
    异步导入一个内容
    - id - 导入内容的id  
    - callback - 回调函数，接受一个导入的对象  
    - 无返回值
  - `popStatus(icon, msg[, doSpark, style, move, time, size])`  
    在底部弹出文本  
    - icon - 图标名称  
    - msg - 要显示的文本  
    - doSpark - 是否会闪烁  
    - style - 样式属性  
    - move - 动画时间  
    - time - 闪烁时间间隔  
    - size - 字体大小
    - 无返回值  
  - `storeDate(k, v)`  
    保存数据
    - k - 键
    - v - 值
    - 无返回值
  - `sysNotification(text[, title, image, onclick])`  
    发送操作系统通知，此API无法设置通知的有效期，通知上的按钮等高级属性
    - text - 通知文本内容  
    - title - 通知标题，默认MCBBS Loader  
    - image - 通知图像链接，默认无图  
    - onclick - 用户点击通知时的回调  
    - 无返回值  
  - `GM`  
    一个含有各个GM函数的对象  
    需要`loader:gm_function`权限才能访问  

请注意所有存储的内容都**不会**在模块移除时自动删除!

以上这些 API 当然是不够用的，但它们是构建辅助 API 所需要的所有原生 API。

你可以通过 `moduleExport` 来编写一些 API。