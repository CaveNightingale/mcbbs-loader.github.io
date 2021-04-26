# API

MCBBS Loader 自身具有如下基本 API，在你的脚本中可以直接调用。

除此之外，MCBBS也提供了一系列的API可供调用。但是Loader并不保证这些API被加载。

使用错误的参数类型调用API可能会抛出Error，但不能保证。

`MCBBS`变量是一个插入在模块头部声明的局部变量，不同的模块所持有的`MCBBS`对象不同，具有loader:earlyload权限的模块在第一次执行时`MCBBS`等于`null`，对象在模块开始执行之前冻结，其结构如下：  

- `MCBBS`
  
  - `getUIVersion()` 获得 UI 版本，如果是旧模板就返回 2，否则返回 3。
  - `page` 页面操作相关，需要 `mcbbs:machine-operate` 权限才能使用，否则将是 `{}`。其中所有 API 均为 V3 设计并且暂时不打算对 V2 提供支持，**请绝对不要在 V2 页面中使用这些 API，否则可能导致意想不到的后果！**
    - `isPostPage()` 判断这个页面是不是一个帖子的浏览页面。
    - `whoPosted()` 获取这个帖子的发表者。
    - // TODO
  
  - `user` 用户操作相关，需要 `mcbbs:usercontrol` 权限才能使用，否则将是 `{}`。
    - `getUserDisplayName()` 获取用户显示名称，如果没有找到将返回 `""`。
    - `getUID()` 获取 UID，如果没有找到将返回 `""`。
  
  - `lodash`
  
    Lodash 支援库
  
  - `$`  
    jQuery 实例  
  - `closeStatus(move)`  
    关闭底部提示  
    - move - 动画持续的时间  
    - 无返回值
  - `createConfig(stgid, name, type, desc, check)`  
    创建配置项  
    - stgid - 一个存储id  
    - name - 在设置页面显示的名字  
    - type - 类型，可以为`'checkbox'`代表复选框，`'texteara'`代表可换行的文本框、`'button'`代表按钮、或者任何其他内容代表不可换行的文本框  
    - desc - 描述，在设置界面的描述  
    - check - 检查函数，在用户输入时调用，用于验证输入的内容是否正确，接受一个用户输入的内容作为value参数（布尔或者字符串类型），返回一个HTML字符串将视为用户输入不合法，并将在配置页面进行提示，返回undefined则将视为用户输入合法，不予提示，特殊地，这个方法在每次`'button'`类型的选项被点击时调用  
    - value - 目前仅`'button'`类型的选项使用，按钮上的文字  
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
    - 返回一个Promise代表运行结果（是否抛出了Error）  
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
  - `mountJS`  
    加入一个&lt;script&gt;标签
    - src - script内容的文件地址（GID或URL）
    - onerror - 出现网络错误时的回调  
    - onsucceed - 加载成功时的回调  
    - 无返回值
  - `mountCSS`  
    加入一个&lt;style&gt;标签
    - src - style内容的文件地址（GID或URL） 
    - onerror - 出现网络错误时的回调  
    - onsucceed - 加载成功时的回调  
    - 无返回值
  - `id`  
    当前API的命名空间，和权限检查有关  
  - `import_(id, callback)`  
    异步导入一个内容
    - id - 导入内容的id  
    - callback - 回调函数，接受一个导入的对象  
    - 返回模块是否能够运行（即已安装且依赖关系满足）  
  - `popInfo(msg)`  
    在底部显示消息  
    - msg - 要显示的消息
    - 无返回值
  - `storeData(k, v)`  
    保存数据  
    - k - 键  
    - v - 值  
    - 无返回值  
  - `sysNotification(text[, title, image, onclick])`  
    发送操作系统通知
    - text - 通知文本内容  
    - title - 通知标题，默认MCBBS Loader  
    - image - 通知图像链接，默认无图  
    - onclick - 用户点击通知时的回调  
    - 无返回值  
  - `isModRunning(id)`  
    检查指定id的模块是否已经安装  
    - id - 模块id  
    - 返回模块是否能够运行（即已安装且依赖关系满足） 
  - `GM`  
    一个含有各个GM函数的对象  
    需要`loader:core`权限才能访问  
  - `LoaderEvent`  
    用于Loader支持的事件的类  
    - `emit(name[, object])`  
      发布一个不可取消的事件  
      - name - 事件名称  
      - object - 事件属性，此对象的全部属性会被复制到事件对象中  
      - 无返回值  
    - `emitCancalable(name[, object])`  
      发布一个可取消的事件  
      - name - 事件名称  
      - object - 事件属性，此对象的全部属性会被复制到事件对象中  
      - 返回事件是否被取消  
  - `crossOriginRequest(details)`  
    用于发起一次跨源请求  
    目前只有 mcbbs.net、github.com、gitee.com 是白名单  
    其他域名的请求会弹出TamperMonkey的跨源请求确认窗口  
    用法和GM_xmlhttpRequest相同，[参考TM文档](https://www.tampermonkey.net/documentation.php?ext=dhdg#GM_xmlhttpRequest)  
  - `acquireCommon()`  
    获取一个`Common`对象，用于少量被Loader封装过的来自MCBBS的common.js的API  
    - 返回值是`Common`对象，其结构如下  
      - loadExtra(script, callback)  
        加载来自MCBBS的一个依赖脚本  
        - script - 脚本名称，例如`'common_extra'`  
        - callback - 回调  
        - 无返回值
      - showOfflineWindow(k, element[, menuv])  
        用于打开一个窗口，不过简化了showWindow的一堆乱七八糟的参数
        - k - 窗口类型  
        - element - 窗口内部的HTML内容，可以是HTML元素对象也可以是字符串  
        - menuv - 和论坛许多API的menuv一样  
        - 无返回值  
  - `GIDURL`  
    一个类，用来表达GID  
    - `fromString(string[, root])`  
      从字符串反序列化GID  
      - string - 字符串  
      - root - 相对路径的当前路径  
      - 返回GID，若字符串无效，返回`GIDURL.NIL`
    - `NIL`  
      表示空的GID
    - `prototype`  
      - `asString()`  
        序列化为字符串  
        - 返回代表GID绝对地址的字符串  
      - `getAsURL(extname)`
        获取对应的URL
        - extname - 文件后缀，需要加`.`
        - 返回GID代表的URL

请注意所有存储的内容都**不会**在模块移除时自动删除!

以上这些 API 当然是不够用的，但它们是构建辅助 API 所需要的所有原生 API。

你可以通过 `moduleExport` 来编写一些 API。