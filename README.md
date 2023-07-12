# effctive-electron

## electron in action

>Electron reads the “main”
entry in our package.json to
determine which file to run
as the main process.

读取`package.json`中的 `main` 决定主进程的文件。
主进程可以创建多个渲染进程。主进程负责和原生的操作系统API交互。
主进程可以使用 `Browser-Window` 创建渲染进程，渲染进程可以加载web页面、展示GUI。可以利用chromium多进程架构。渲染进程互相隔离，不能访问操作系统 API

---

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

### main process

1. 导入 electron

require 引入 electron 包。

### 渲染进程

主进程和 OS 交互，管理状态，协调所有其他进程
渲染进程负责渲染 css 和 html。
webContext 加载 html

electron 可以用 浏览器的属性， 也可用 node 的属性。模糊了*客户端*和*服务端*的边界。

将渲染进程代码放到单独文件中。

html 引用 js：`src` 属性 vs `require` 模块

### 实现 UI

写 html， 类似 qt 信号槽

### 跨域请求

fetch 访问外部链接。链式调用。
**promise**， await

### preload & 进程间通信

*preload.js* 通过预加载脚本将需要的 API 暴露给渲染进程。
渲染进程无法访问 node.js 接口。

**进程间通信**的方式：

ipcRender, ipcMain：渲染进程和主进程通信。
**remote** 模块，
**contextBridge**模块。

渲染进程 => 主进程：ipcRenderer.send
渲染进程 <=> 主进程： ipcRenderer.invoke
主进程 => 渲染进程: webContents.send

---

## 正式开发

### 调试渲染进程

1. 默认菜单里提供了。
2. 代码触发 `openDevTools`

### 调试主进程

vscode

---

## misc

### 代理配置

删除代理

### 坑

1. npm start 报错。原因可能是 node 版本太老， electron 版本太新， 重新安装 老版本 electron 后 npm start 无问题。


2. **在 html 里写的 scrpit 不生效。**
可能书中的环境是 mac。和 windows 不同。

3. **require module 不生效。**

渲染进程不支持 require。

书中的示例代码可能太老，函数签名有变化，需要修改。

4. **lambda** 的坑：以下 lambda 的区别：

```json

map(num => num * num);

map((num) => { num * num; });

```

一个有返回值，一个没有返回值。

5. preload.js require marked报错：`Error: module not found: marked`

electron 中的[进程沙盒化](https://www.electronjs.org/zh/docs/latest/tutorial/sandbox)，
preload 只能 require 部分包。

[electron module not find](https://stackoverflow.com/questions/58653223/why-does-preload-js-return-error-module-not-found)

---

## js 语法

1. document元素的 value


## css & html

确实好用
