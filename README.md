# effctive-electron

## electron in action

>Electron reads the “main”
entry in our package.json to
determine which file to run
as the main process.

读取`package.json`中的 `main` 决定主进程的文件。
主进程可以创建多个渲染进程。主进程负责和原生的操作系统API交互。
主进程可以使用 `Browser-Window` 创建渲染进程，渲染进程可以加载web页面、展示GUI。可以利用chromium多进程架构。渲染进程互相隔离，不能访问操作系统 API

## start

### 初始化

**package.json**

用于 node 项目， npm init 生成

### electron install

**下载 electron **

`npm install electron --save-dev `


## misc

### 代理配置

