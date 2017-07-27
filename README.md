# electron
Electron quick start and packaging

## 初步理解
###### 简介
Electron 可以让你使用纯 JavaScript 调用丰富的原生 APIs 来创造桌面应用。你可以把它看作是专注于桌面应用而不是 web 服务器的，io.js 的一个变体。
这不意味着 Electron 是绑定了 GUI 库的 JavaScript。相反，Electron 使用 web 页面作为它的 GUI，所以你能把它看作成一个被 JavaScript 控制的，精简版的 Chromium 浏览器。

###### 主进程
在 Electron 里，运行 package.json 里 main 脚本的进程被称为主进程。在主进程运行的脚本可以以创建 web 页面的形式展示 GUI。
###### 渲染进程
由于 Electron 使用 Chromium 来展示页面，所以 Chromium 的多进程结构也被充分利用。每个 Electron 的页面都在运行着自己的进程，这样的进程我们称之为渲染进程。
在一般浏览器中，网页通常会在沙盒环境下运行，并且不允许访问原生资源。然而，Electron 用户拥有在网页中调用 io.js 的 APIs 的能力，可以与底层操作系统直接交互。
###### 主进程与渲染进程的区别
主进程使用 BrowserWindow 实例创建网页。每个 BrowserWindow 实例都在自己的渲染进程里运行着一个网页。当一个 BrowserWindow 实例被销毁后，相应的渲染进程也会被终止。
主进程管理所有页面和与之对应的渲染进程。每个渲染进程都是相互独立的，并且只关心他们自己的网页。
由于在网页里管理原生 GUI 资源是非常危险而且容易造成资源泄露，所以在网页面调用 GUI 相关的 APIs 是不被允许的。如果你想在网页里使用 GUI 操作，其对应的渲染进程必须与主进程进行通讯，请求主进程进行相关的 GUI 操作。
在 Electron，我们提供用于在主进程与渲染进程之间通讯的 [ipc](https://github.com/electron/electron/blob/master/docs-translations/zh-CN/api/ipc-main-process.md) 模块。并且也有一个远程进程调用风格的通讯模块 [remote](https://www.w3cschool.cn/electronmanual/electronmanual-remote.html)。


## 运行Electron应用
1. num install
2. electron .

## 详细入门及安装过程，请点击下面的链接
   [http://www.jianshu.com/p/900a961efc6c](http://www.jianshu.com/p/900a961efc6c)