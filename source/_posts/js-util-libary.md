---
title: 收集一些实用的前端js工具库【不定时更新】
date: 2020-04-20 16:59:35
tags: ["frontend", "js", "node"]
---

## 十进制运算

### [big.js](https://github.com/MikeMcl/big.js)

> 一个小型，快速的JavaScript库，用于任意精度的十进制算术运算。

### [bignumber.js](https://github.com/MikeMcl/bignumber.js)

> 一个用于任意精度十进制和非十进制算术的JavaScript库。

### [decimal.js](https://github.com/MikeMcl/decimal.js)

> JavaScript的任意精度的十进制类型。

<!-- more -->

## 时间处理

### [dayjs](https://github.com/iamkun/dayjs)

> 只有2KB的时间处理库，使用方式如同 `Moment API`，可以通过添加插件实现更多功能。

## 垫片

### [promise.allsettled](https://github.com/es-shims/promise.allsettled)

> 当前版本的 `Promise` 提供了 `.all()` 静态方法，用于合并一系列 `Promise` 的结果。
>
> 然而，由于单一 `Promise` 进入 `rejected` 状态便会立即让 `Promise.all()` 的结果进入 `rejected` 状态，以至于通过 `Promise.all()` 进入 `rejected` 状态时，其中的源 `Promise` 仍然可能处于 `pending` 状态，以至于无法获得所有 `Promise` 完成的时机。
>
> `Promise.allSettled()` 静态方法会等待所有源 `Promise` 进入 `fulfilled` 或者 `rejected` 状态，从而确保不会造成时序上的冲突。



### [Promise.prototype.finally](https://github.com/es-shims/Promise.prototype.finally)

> 给`Promise`实例添加 `.finally`方法，以保证代码无论在`Promise`的`resolve`或者`reject`时被执行。

## 异步处理

### [await-to-js](https://github.com/scopsy/await-to-js)

> 用于异步等待包装器，可轻松处理错误，而无需尝试捕获；可将任意`Promise` 转换为`[err, data]`的数组返回值，方便平铺逻辑代码，不使用`.catch`和`try/catch`来捕捉错误，从而减少代码嵌套。



## 数据处理/实用工具

### [lodash](https://github.com/lodash/lodash)

> 现代化的JavaScript实用程序库，提供模块化，高性能和附加功能。

### [ramda](https://github.com/ramda/ramda)

> 一个专门为函数式编程风格设计的库，每个方法会返回新的函数或者值，不会改变原始值。

### [licia](https://github.com/liriliri/licia)

> Licia 是一套在开发中实践积累起来的实用 JavaScript 工具库。该库目前拥有超过 400 个模块，包括 Dom 操作，cookie 设置，类创建，模板函数，日期格式化等实用模块，同时配套有打包工具 Eustia 进行定制化，使JS脚本加载量缩减在 10KB 以下，极大优化移动端页面的加载速度。

### [collect.js](https://github.com/ecrmnn/collect.js)

> 方便且无依赖的工具库，用于处理数组和对象。

## 模拟数据

### [Mock](https://github.com/nuysoft/Mock)

> Mock.js是一个模拟数据生成器，可帮助前端开发和原型与后端进度分开，并减少某些单调性，尤其是在编写自动化测试时。

### [chancejs](https://github.com/chancejs/chancejs)

> Chancejs 是生成随机字符串，数字等的极简主义生成器，以帮助减少某些单调性，尤其是在编写自动测试或任何您需要任何随机值的地方。

## 字符串处理

### [qs](https://github.com/ljharb/qs)

> 具有嵌套支持的`querystring`解析器。

### [voca](https://github.com/panzerdp/voca)

> Voca是一个用于处理字符串的JavaScript库。

```js
v.camelCase('bird flight');              // => 'birdFlight'
v.sprintf('%s costs $%.2f', 'Tea', 1.5); // => 'Tea costs $1.50'
v.slugify('What a wonderful world');     // => 'what-a-wonderful-world'
```



## 加解密

### [crypto-js](https://github.com/brix/crypto-js)

> 加密标准的JavaScript库。

### 字节格式化

### [pretty-bytes](https://github.com/sindresorhus/pretty-bytes)

> 将字节转换为人类可读的字符串：1337→1.34 kB

## 图片懒加载

### [lazyload](https://github.com/tuupola/lazyload)

> 使长网页中图像延迟加载，
> 用户滚动到窗口可视范围内的图像之前，不会加载它们。
> 这与图像预加载相反。

### [lazysizes](https://github.com/aFarkas/lazysizes)

> 高性能和SEO友好的惰性加载器，用于图像，iframe等，可检测用户交互，CSS或JavaScript触发的可见性更改，而无需进行配置。

## 图片预览

### [viewerjs](https://github.com/fengyuanchen/viewerjs)

> JavaScript image viewer. 

### [lightbox2](https://github.com/lokesh/lightbox2)

> 一个灯箱效果的图片展示插件。

### [medium-zoom](https://github.com/francoischalifour/medium-zoom)

> 一个模仿 `medium`的图片查看JavaScript库

## http请求

### [axios](https://github.com/axios/axios)

> 基于`Promise`的`HTTP`客户端，用于浏览器和`node.js`

### [fly](https://github.com/wendux/fly)

> 支持所有`JavaScript`运行时的请求转发和基于`Promise`的`HTTP`客户端。

## 数据可视化/图表

### [echarts](https://echarts.apache.org/)

> 一个使用 `JavaScript` 实现的开源可视化库，可以流畅的运行在 `PC` 和移动设备上，兼容当前绝大部分浏览器`（IE8/9/10/11，Chrome，Firefox，Safari等）`，底层依赖矢量图形库 [ZRender](https://github.com/ecomfe/zrender)，提供直观，交互丰富，可高度个性化定制的数据可视化图表。

### [antv](https://antv.vision/)

> `AntV` 是蚂蚁金服全新一代数据可视化解决方案，致力于提供一套简单方便、专业可靠、无限可能的数据可视化最佳实践。

### [d3](https://github.com/d3/d3)

> 通过`SVG`，`Canvas`和`HTML`使数据栩栩如生。

## 手势

### [any-touch](https://github.com/any86/any-touch)

> 手势库, 按需2kb~5kb, 支持PC / 手机 / 微信端。

### [hammer.js](https://github.com/hammerjs/hammer.js)

> 一个用于多点触控手势的JavaScript库。

## 拖拽

### [draggabilly](https://github.com/desandro/draggabilly)

> 一个专注于拖拽功能的 JS 库。

### [dragula](https://github.com/bevacqua/dragula)

> 拖放是如此简单。

### [Sortable](https://github.com/SortableJS/Sortable)

> Sortable.js是一款轻量级的拖放排序列表的js插件（虽然体积小，但是功能很强大）。

## 加载进度条

### [nprogress](https://github.com/rstacruz/nprogress)

> 适用于`Ajax`应用程序的超薄进度条。
> 受到`Google`，`YouTube`和`Medium`的启发。

### [qier-progress](https://github.com/vortesnail/qier-progress)

> `qier-progress` 用于缓解用户焦虑的进度条，它优美且简单，在你的网页发送请求或跳转网站的时候使用它吧！当然，还可以用于一些文件上传或加载场景。如果你知道 [nprogress](https://github.com/rstacruz/nprogress)，那你对这个插件就更不会陌生了。

## 文件保存

### [FileSaver.js](https://github.com/eligrey/FileSaver.js)

> 一个`HTML5 saveAs（）` 的实现

## 调试

### [vConsole](https://github.com/Tencent/vConsole)

> 腾讯团队出品，用于移动网页的轻量级，可扩展的前端开发人员工具。

### [eruda](https://github.com/liriliri/eruda)

> Eruda 是一个专为手机网页前端设计的调试面板，类似 DevTools 的迷你版，其主要功能包括：捕获 console 日志、检查元素状态、捕获XHR请求、显示本地存储和 Cookie 信息等等。

### [spy-debugger](https://github.com/wuchangming/spy-debugger)

> 微信调试，各种WebView样式调试、手机浏览器的页面真机调试。便捷的远程调试手机页面、抓包工具，支持：HTTP/HTTPS，无需USB连接设备。

## 富文本编辑器

### [jodit](https://github.com/xdan/jodit)

> Jodit-最佳“所见即所得”编辑器

### [Trumbowyg](https://github.com/Alex-D/Trumbowyg)

> 轻巧而惊人的 JavaScript富文本编辑器-仅20kB（gzip之后仅8kB）

### [summernote](https://github.com/summernote/summernote)

> 超级简单的所见即所得编辑器