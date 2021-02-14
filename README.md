# WL-1 欢迎使用

<div style='text-align:center;'><strong><span style='font-size:32px;color:#df307f;'>MCBBS Loader 是 MCBBS 模块加载器</span></strong></div>

<br/>

<div style='text-align:center;'><span style='font-size:16px;color:#df307f;'>加载你喜欢的模块到 MCBBS 中，解锁更多技能！</span></div>

---

Git 仓库：

<i class="fa fa-code"></i> https://github.com/MCBBS-Loader/MCBBS-Loader-Core/

## 快速安装

<div class="alert alert-info"><i class="fa fa-info-circle"></i> 下面的安装选项需要先 <a href='https://www.tampermonkey.net' target='_blank' class='alert-link'>安装 TamperMonkey</a> </div>

<div><a style='color:#ffffff' class='btn btn-primary' href='https://cdn.jsdelivr.net/gh/MCBBS-Loader/MCBBS-Loader-Core@main/dist/nightly.bundle.prod.user.js' target='_blank'><i class="fa fa-download"></i> 立即安装</a>&nbsp; 仓库实时更新。</div>

---

## 什么是 MCBBS Loader？

MCBBS Loader 可以加载符合要求的模块到 MCBBS 中，正如同 Forge 可以将符合要求的模组加载到 Minecraft 中。

## 我如何安装它？

1. MCBBS Loader 是一个**用户脚本**，所以你需要一款用户脚本管理器。MCBBS Loader 的所有分支都在 TamperMonkey 上完成过测试。理论上 ViolentMonkey 也可以运行 MCBBS Loader。

   <div class="alert alert-info"><i class="fa fa-info-circle"></i> 从 <a href='https://www.tampermonkey.net' target='_blank' class='alert-link'>这里</a> 获得 TamperMonkey。</div>

   <div class="alert alert-warning"><i class="fa fa-exclamation-triangle"></i> TamperMonkey <b>不是自由软件</b>，它甚至<b>没有开放源代码</b>！如果你对专有软件深恶痛绝，请考虑帮我们移植相关代码以在自由的脚本管理器上运行。</div>

2. 安装了 TamperMonkey 后，刷新本页，单击上方的「立即安装」按钮：

   - 该脚本会随着我们的每次构建而更新，所有的构建在提交前都经过测试。
   
3. 打开 MCBBS，将鼠标移至右上角你的头像上，如果看到「MCBBS 模块管理」字样，那么恭喜，MCBBS Loader 已经部署在你的浏览器上！

   <div class="alert alert-info"><i class="fa fa-info-circle"></i> MCBBS Loader 的加载需要时间，请耐心等待。</div>

---

## 使用方法

当你安装了 MCBBS Loader 后，单击用户菜单中的「MCBBS 模块管理」即可进入管理界面。

![open](https://i.loli.net/2021/01/01/5jES8pGtH3BWTkC.png)

在模块管理界面的下方，你可以使用「预览软件源」的方法来探索模块，也可以通过使用别人提供给你的 ID 进行安装。

![Manager](https://i.loli.net/2021/01/01/3IVpHd2JF7tsr9C.png)

<div class="alert alert-warning"><i class="fa fa-exclamation-triangle"></i> 这些软件源仍在开发中，你预览到的可能仍旧是空列表。</div>

- **调试模式** 允许你使用源代码安装模块，这通常在你开发模块需要测试而又不想遇到 MCBBS Loader 的自动更新特性时非常有用。
- **查看源代码** 允许你查看某个模块的源代码并修改它。
- **启用/禁用** 可以控制模块的启停。
- **删除模块** 可以移除模块。**注意，没有二次确认！**

有些模块提供了**模块配置**，你可以在管理界面进行配置。

![Menu](https://i.loli.net/2021/01/01/fiJyRISgCbVp9nq.png)

![Conf](https://i.loli.net/2021/01/01/9wuhDQkotylqPKX.png)

## 我想编写模块……

所有用户都应该具备编写模块的能力！

阅读 [TR-1 世界真的在那里吗？](./new/TR-1.md) 来了解如何开发一个模块。

## 我能修改 MCBBS Loader 吗？

完全没问题！MCBBS Loader 是自由软件，使用 [GNU General Public License Version 3](https://gnu.org/licenses/gpl-3.0.html) 授权。

> 是的，把它贡献出来。  - Richard Stallman

如果你能将修改的部分通过 Pull Request 的方式发送给我们，我们会不胜感激。不过，按照许可证要求，你没有这样做的义务。

## MCBBS Loader 和其它脚本冲突吗？

我们在设计加载器和 API 时都尽量避免了冲突，但脚本多种多样，我们实难保证这一点。如果你发现了冲突，可以通过 Issue 向我们汇报。

同时亦请注意，多个脚本会降低载入速度，因为它们在页面载入前加载；而 MCBBS Loader 的多个模块不会，因为它们在页面载入后再加载。

## 开发人员

- [RarityEG](https://www.mcbbs.net/home.php?mod=space&uid=3281025)：加载器骨架、API 编写、文档编写、加载实现
- [洞穴夜莺](https://www.mcbbs.net/home.php?mod=space&uid=2853776)：样式美化、API 编写、依赖功能实现、文档编写