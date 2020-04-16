---
title: electron使用flash插件
date: 2016-10-16 11:52:35
categories: ["frontend", "summaries"]
tags: ["electron", "node"]
---

## 需求
> 最近有个需求是使用Electron开发一个Windows直播的客户端，使用Flash进行播放相关功能，但是Electron的Flash功能需要插件支持，折腾好久才搞定，做个记录。  
### 创建项目
#### 安装electron  
```bash
$ npm install electron -g
```
#### 创建项目
```bash
$ mkdir test
$ cd test/
$ touch package.json
$ touch main.js
```
> package.json  
```json
{
  "name": "test",
  "version": "1.0.0",
  "main": "main.js"
}
```
> main.js  
```js
const {app, BrowserWindow} = require('electron')
const {resolve} = require('path')
const url = require('url')
// 注册Flash插件
const flashplayer = resolve(__dirname, 'pepflashplayer.dll')
app.commandLine.appendSwitch('ppapi-flash-path', flashplayer);
app.commandLine.appendSwitch('ppapi-flash-version', '23.0.0.194');
// 保持一个对于 window 对象的全局引用，如果你不这样做，
// 当 JavaScript 对象被垃圾回收， window 会被自动地关闭
let win
function createWindow() {
  // 创建浏览器窗口。
  win = new BrowserWindow({
    width: 800,
    height: 600,
    webPreferences: { // 注意一定要 添加这个 不然flash插件不会生效
      plugins: true
    }
  })
  // 随便加载一个flash视频页面
  win.loadURL('http://www.iqiyi.com/v_19rrarwio8.html?list=19rrkp73da')
  // 打开开发者工具。
  win.webContents.openDevTools()
  // 当 window 被关闭，这个事件会被触发。
  win.on('closed', () => {
    // 取消引用 window 对象，如果你的应用支持多窗口的话，
    // 通常会把多个 window 对象存放在一个数组里面，
    // 与此同时，你应该删除相应的元素。
    win = null
  })
}
// Electron 会在初始化后并准备
// 创建浏览器窗口时，调用这个函数。
// 部分 API 在 ready 事件触发后才能使用。
app.on('ready', createWindow)
// 当全部窗口关闭时退出。
app.on('window-all-closed', () => {
  // 在 macOS 上，除非用户用 Cmd + Q 确定地退出，
  // 否则绝大部分应用及其菜单栏会保持激活。
  if (process.platform !== 'darwin') {
    app.quit()
  }
})
app.on('activate', () => {
  // 在这文件，你可以续写应用剩下主进程代码。
  // 也可以拆分成几个文件，然后用 require 导入。
  if (win === null) {
    createWindow()
  }
})
```
#### 放置dll文件
+ 如果你有安装Chrome浏览器，可以在地址栏输入`chrome://plugins/`，点击右侧的详细信息，找到`Adobe Flash Player`条目，在位置项复制`pepflashplayer.dll` (**Windows**)文件到项目目录。
+ 单独安装请打开官方下载页面 `http://get2.adobe.com/cn/flashplayer/otherversions/`，选择你的操作系统，版本选择`for Opera and Chromium-PPAPI`结尾的版本。安装完毕后:
    - 在`C:\Windows\SysWOW64\Macromed\Flash`下找到32位版本如：`pepflashplayer32_24_0_0_194.dll`(名称和版本号可能有出入)。 
    - `在C:\Windows\System32\Macromed\Flash`下找到64位版本，如：`pepflashplayer64_24_0_0_194.dll`(名称和版本号可能有出入)。
    - 然后复制到项目目录，重命名为`pepflashplayer.dll`即可。

#### 启动测试
> 接着运行 `$ electron .` 打开一个爱奇艺视频链接，发现可以加载咯。
