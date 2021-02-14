# TR-2 模块信息

你可能已经注意到，在模块的开头都有这样的**模块信息**：

```javascript
/* MCBBS Module
id = examplemod
author = xxx
*/
```

下面我们逐行进行分析：

- 一个模块**必须**以 `/* MCBBS Module` 开头，前面**不得**有任何其它字符。
- 采用键值对的形式填写信息，一行一个。

如果你编写过 TamperMonkey 脚本，也许你会更好地理解这段信息的作用。

你可以存储任何你想要的信息在这里，详细信息参阅[元信息](./dev/meta.md)章节，这里我们只介绍常用的几种：



- id：**必填**，模块唯一识别 ID，是模块的身份证，建议使用Java语言包名命名方式，详细信息参考[杂项](./dev/misc.md)中的模块ID章节。

- name：选填，模块的显示名称，可以使用 HTML。如果不填，默认和你的 ID 相同。

- author：选填，你的名字，可以使用 HTML。如果不填，默认为 `Someone`。

- description：选填，模块描述，可以使用 HTML。如果不填，默认为 `No description provided.`。

- version：选填，版本号，检查更新时使用。不填则为 `undefined`。

- updateURL：选填，检查更新时会从该 URL 更新脚本。需要和 version 字段一起用。不填则为 `undefined`。可以使用 ML Global ID。

- icon：选填，模块图标。可以使用图片 CDN，也可以使用 BASE64 编码，例如：

  ```
  data:image/png;base64,iVBORw0KGgoAAAANSUh...（后略）
  ```
