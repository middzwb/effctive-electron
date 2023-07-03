# effctive-electron

## electron in action

>Electron reads the “main”
entry in our package.json to
determine which file to run
as the main process.

读取`package.json`中的 `main` 决定主进程的文件。
主进程可以创建多个渲染进程。主进程负责和原生的操作系统API交互。
主进程可以使用 `Browser-Window` 创建渲染进程，渲染进程可以加载web页面、展示GUI。可以利用chromium多进程架构。渲染进程互相隔离，不能访问操作系统 API

## 练手

### 项目初始化

**package.json**

用于 node 项目， npm init 生成

### electron install

**下载 electron **

`npm install electron --save-dev `

### package.json

package.json 中的 scripts。

npm start: 执行package.json中的脚本

### 处理main process

1. 导入 electron

### 渲染进程

主进程和 OS 交互，管理状态，协调所有其他进程
渲染进程负责渲染 css 和 html。
webContext 加载 html

electron 可以用 浏览器的属性， 也可用 node 的属性。模糊了*客户端*和*服务端*的边界。

将渲染进程代码放到单独文件中。

html 引用 js：`src` 属性 vs `require` 模块

**疑问**

在 html 里写的 scrpit 不生效。

## misc

### 代理配置

