<div style='text-align:center;'><strong><span style='font-size:32px;color:#df307f;'>MCBBS Loader 是 MCBBS 模块加载器</span></strong></div>

<br/>

<div style='text-align:center;'><span style='font-size:16px;color:#df307f;'>加载你喜欢的模块到 MCBBS 中，解锁更多技能！</span></div>

---

<i class="fa fa-code"></i> https://github.com/MCBBS-Loader/MCBBS-Loader-Core/

## 快速安装

<div class="alert alert-info"><i class="fa fa-info-circle"></i> 下面的三个快速安装选项需要先 <a href='https://www.tampermonkey.net' target='_blank' class='alert-link'>安装 TamperMonkey</a> </div>

<div><span font-size='1.8rem'><a  style='color:#ffffff' class='btn btn-primary' href="https://cdn.jsdelivr.net/gh/MCBBS-Loader/MCBBS-Loader-Core@stable/dist/stable.bundle.prod.user.js" target='_blank'><i class="fa fa-download"></i> 下载稳定版</a></span>&nbsp;来获取经过测试的稳定更新。<br/><br/><a style='color:#ffffff' class='btn btn-success' href='https://cdn.jsdelivr.net/gh/MCBBS-Loader/MCBBS-Loader-Core@dev/dist/dev.bundle.prod.user.js' target='_blank'><i class="fa fa-wrench"></i> 下载开发版</a>&nbsp;来获取速度与稳定折中的更新。<br/><br/><a style='color:#ffffff' class='btn btn-dark' href='https://cdn.jsdelivr.net/gh/MCBBS-Loader/MCBBS-Loader-Core@main/dist/nightly.bundle.prod.user.js' target='_blank'><i class="fa fa-bug"></i> 下载同步版</a>&nbsp;来和我们的仓库保持完全同步。<strong>小心 Bug！</strong></div>

---

## 什么是 MCBBS Loader？

MCBBS Loader 可以加载符合要求的模块到 MCBBS 中，正如同 Forge 可以将符合要求的模组加载到 Minecraft 中。

## 我如何安装它？

1. MCBBS Loader 是一个**用户脚本**，所以你需要一款用户脚本管理器。MCBBS Loader 的所有分支都在 TamperMonkey 上完成过测试。理论上 ViolentMonkey 也可以运行 MCBBS Loader。

   <div class="alert alert-info"><i class="fa fa-info-circle"></i> 从 <a href='https://www.tampermonkey.net' target='_blank' class='alert-link'>这里</a> 获得 TamperMonkey。</div>

   <div class="alert alert-warning"><i class="fa fa-exclamation-triangle"></i> TamperMonkey <b>不是自由软件</b>，它甚至<b>没有开放源代码</b>！如果你对专有软件深恶痛绝，请考虑帮我们移植相关代码以在自由的脚本管理器上运行。</div>

2. 安装了 TamperMonkey 后，刷新本页，单击上方「快速安装」中的任意一个选项：

   - 稳定版（Stable）：这个分支的**每个**更新在发布之前都经过测试，拥有最少的漏洞。
   - 开发版（Dev）：这个分支的大多数更新**应当**是较稳定的，它的更新速度更快。
   - 同步版（Nightly）：这个分支更新速度最快，它几乎随着**每次**提交**都会**发布一个更新，也正因为如此，它不太稳定，Bug 随时都可能出现。

3. 打开 MCBBS，将鼠标移至右上角你的头像上，如果看到「MCBBS 模块管理」字样，那么恭喜，MCBBS Loader 已经部署在你的浏览器上！

   <div class="alert alert-info"><i class="fa fa-info-circle"></i> MCBBS Loader 的加载需要时间，请耐心等待。</div>

---

## 我如何安装模块？

你可以在 MCBBS 或 GitHub 上找到一些模块。在我们的[账号](https://github.com/MCBBS-Loader/)中也有很多模块。

模块的发布者一般会提供给你以下三条信息之一：

- 模块的网络资源 URL（常见于需要长期更新的模块）
- 模块的 BASE64 编码（不常用）
- 模块的 JavaScript 源代码（常用于不需要更新或一次性的模块）

1. 打开「MCBBS 模块管理」：

   ![Manager](https://i.loli.net/2020/11/14/GfwhDYbAlQ7r4Fv.png)

2. 粘贴 URL，BASE64 或 JavaScript 代码到「安装新模块」文本框中，单击「安装」按钮，模块即被安装在加载器中。

   <div class="alert alert-info"><i class="fa fa-info-circle"></i> 在有些系统上，安装成功时系统会弹出一条通知提醒你。</div>

## 我想编写模块……

阅读 [模块开发文档](dev.md) 来了解如何开发一个模块。

## 我能修改 MCBBS Loader 吗？

完全没问题！MCBBS Loader 是自由软件，使用 [GNU General Public License Version 3](https://gnu.org/licenses/gpl-3.0.html) 授权。

> 是的，把它贡献出来。  - Richard Stallman

如果你能将修改的部分通过 Pull Request 的方式发送给我们，我们会不胜感激。不过，按照许可证要求，你没有这样做的义务。

## MCBBS Loader 和其它脚本冲突吗？

我们在设计加载器和 API 时都尽量避免了冲突，但脚本多种多样，我们实难保证这一点。如果你发现了冲突，可以通过 Issue 向我们汇报。

同时亦请注意，多个脚本会降低载入速度，因为它们在页面载入前加载；而 MCBBS Loader 的多个模块不会，因为它们在页面载入后再加载。

## 开发人员

- [RarityEG](https://www.mcbbs.net/home.php?mod=space&uid=3281025)：加载器、API、文档