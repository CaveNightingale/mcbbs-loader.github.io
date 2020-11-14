# 快速上手

本节展示了一个简单的 MCBBS 模块，来告诉你如何着手开发一个模块。

1. 你需要学习 JavaScript，你可以参考 [JavaScript 教程](https://www.runoob.com/js/js-tutorial.html) 来完成。不要担心，JavaScript 很容易学！（我只花了 50 分钟）

2. 打开 MCBBS 模块管理器，在「安装新模块」的文本框中输入：

   ```javascript
   // MCBBS-Module
   // @id test.helloworld
   // -MCBBS-Module
   ```

   这里我们只填写了 ID 数据值，因为只有它是必需的。

   请注意空格，每一行在 `//` 后都有一个空格。

3. 在 `// -MCBBS-Module` 以下的部分就是代码，将被嵌入页面执行。

   我们在后面追加：

   ```javascript
   alert("Hello World!");
   ```

   现在整体代码看起来像这样：

   ```javascript
   // MCBBS-Module
   // @id test.helloworld
   // -MCBBS-Module
   alert("Hello World!");
   ```

4. 单击「安装」按钮，页面会刷新，你将看到你的模块和弹出的 「Hello World!」提示框。

   ![Hello World](https://i.loli.net/2020/11/14/XPTrxD1fe3muhgd.png)

祝贺你！你已经完成了你的第一个模块！要继续，请参看后续的章节。