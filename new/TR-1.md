# TR-1 世界真的在那里吗？

MCBBS Loader 的每个用户，都应当具有编写模块的能力。

编写模块不仅十分直观，还能够更快扩展 MCBBS 的功能。

通过本教程来编写一个简单的模块，并感受 MCBBS Loader 的特点。

**现在就开始！**

1. 如果你还没有安装 MCBBS Loader，请参考首页的说明安装它。

2. 登录 MCBBS，将鼠标悬浮到右上角你的头像上，单击「MCBBS 模块管理」打开管理页面。

3. 单击一下「调试模式」，在「安装新模块」中输入：

   ```javascript
   /* MCBBS Module
   id = me.example
   name = Hello World
   description = Hello MCBBS Loader!
   author = 你的名字
   */
   alert("Hello World!");
   ```

   ![Code](https://i.loli.net/2021/01/01/yljsIqAdtoMeFaf.png)

4. 单击「安装」，你的第一个模块便完成了！

5. 现在刷新页面，可以看到「Hello World!」字样。

<button type='button' class="btn btn-info" style="width:100%;transition:500ms;" onclick="$('#hideEle').show();this.onclick=function(){};this.className='btn btn-success';this.innerHTML=this.innerHTML.replace('question','check').replace('你完成了吗？','恭喜！');var ev = ev || window.event;new Firework(ev.clientX, ev.clientY).init();"><i class="fa fa-question"></i> 你完成了吗？</button>

<div id='hideEle' style='display:none;'>


你完成了你的第一个模块，恭喜！MCBBS Loader 拥有简洁的 API 和完备的依赖系统。此外，移植而来的事件系统能提供额外的帮助。

> “如果说我看得远，那是因为我站在巨人的肩膀上。”
>
> —— 艾萨克·牛顿

继续阅读以了解如何使用 MCBBS Loader 构建精巧的模块。前往 [TR-2](./new/TR-2.md)。

</div>

