# 兼容性
## 手机兼容性

目前LoaderCore唯一官方支持的手机浏览器是yandex浏览器。它可以兼容crx版本的TamperMonkey。

如果您有任何在其他浏览器上运行LoaderCore的思路，请联系我们。

[Yandex Android (Google Play)](https://play.google.com/store/apps/details?id=com.yandex.browser&referrer=promopage)

[Yandex IOS (App Store)](https://itunes.apple.com/ru/app/yandex.browser-for-iphone/id483693909)

请注意，许多为电脑设计的模块在手机上使用起来体验比较糟糕。并且我们目前手机上出现问题时能采集到的信息十分有限，或许将来会有LoaderCore层面的采集报错的功能，但现在还没有。目前为止LoaderCore的管理页面等不在手机版界面上显示，如需查看请切换到电脑版。

## v3模板兼容性

LoaderCore及LoaderMin与论坛v3模板完全兼容，但是模块不一定兼容。

## 关于LoaderMin

LoaderMin是LoaderCore的一个变种，它的体积仅有LoaderCore的1/4到1/3而几乎兼容所有现有的LoaderCore模块，只有使用MCBBS.popStatus和MCBBS.$的程序可能会在LoaderCore和LoaderMin上运行时行为不同，此外LoaderMin与LoaderCore在管理页面上有细微不同。LoaderMin没有计划成为LoaderCore的主分支。

[MCBBS Loader Min (Compressed)](https://gitee.com/CaveNightingale/MCBBS-Loader-Core/raw/min/dist/nightly.bundle.prod.user.js)

[MCBBS Loader Min (Debuggable)](https://gitee.com/CaveNightingale/MCBBS-Loader-Core/raw/min/dist/nightly.bundle.dev.user.js)

## 与其他第三方脚本的兼容性

在v2模板下与常见的脚本均兼容。saltMCBBS在v3模板不但运行不正常而且会搞坏LoaderCore的页面。