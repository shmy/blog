---
title: 纯CSS实现六边形布局和排列
date: 2020-04-17 09:52:15
categories: ["frontend", "summaries"]
tags: ["css"]
---

## 前言

> 最近新上一个项目，有个页面需要实现六边形布局排列，如下图（敏感数据打了马赛克）：

![8QUxuaHmG2E1keM](https://i.loli.net/2020/04/16/8QUxuaHmG2E1keM.png)

<!-- more -->

> 需要实现以上布局，并且能够根据屏幕宽度自动调整每行的个数；

## 先画一个六边形

```html
<div class="container">
  <div class="hex"></div>
</div>
```

```scss
$hexWidth: 120px;
$hexHeight: 130px;
.container{
  margin: 0 auto;
  font-size: 0;
  width: 768px;
}
.hex {
  display: inline-block;
  position: relative;
  width: $hexWidth;
  height: $hexHeight;
  background: #64c7cc;
  margin-left: $gapWidth;
  -webkit-clip-path: polygon(0 25%,50% 0,100% 25%,100% 75%,50% 100%,0 75%);
  clip-path: polygon(0 25%,50% 0,100% 25%,100% 75%,50% 100%,0 75%);
}
```



![GZEx2e6f9srKzLX](https://i.loli.net/2020/04/16/GZEx2e6f9srKzLX.png)



> 关于 `clip-path`的兼容性请参考：[CSS clip-path property (for HTML)](https://caniuse.com/#feat=css-clip-path)
>
> 关于`clip-path`的在线调试请参考: [CSS clip-path maker](https://bennettfeely.com/clippy/)

## 排列多个六边形

```html
<div class="container">
  <div class="hex">
  </div>
  <div class="hex">
  </div>
  <div class="hex">
  </div>
  <div class="hex">
  </div>
  <div class="hex">
  </div>
  <div class="hex">
  </div>
  <div class="hex">
  </div>
  <div class="hex">
  </div>
  <div class="hex">
  </div>
  <div class="hex">
  </div>
  <div class="hex">
  </div>
  <div class="hex">
  </div>
  <div class="hex">
  </div>
  <div class="hex">
  </div>
  <div class="hex">
  </div>
</div>
```

![2Ec9aYIAsV4Q5ep](https://i.loli.net/2020/04/16/2Ec9aYIAsV4Q5ep.png)

### 增加间隙

```scss
$hexWidth: 120px;
$hexHeight: 130px;
$gapWidth: 10px;
.container{
  margin: 0 auto;
  font-size: 0;
  width: 768px;
}
.hex {
  display: inline-block;
  position: relative;
  width: $hexWidth;
  height: $hexHeight;
  margin-left: $gapWidth;
  background: #64c7cc;
  -webkit-clip-path: polygon(0 25%,50% 0,100% 25%,100% 75%,50% 100%,0 75%);
  clip-path: polygon(0 25%,50% 0,100% 25%,100% 75%,50% 100%,0 75%);
}
```



![L8vNo9AWs2pgYG7](https://i.loli.net/2020/04/16/L8vNo9AWs2pgYG7.png)



### 让偶数行偏移

```scss
$hexWidth: 120px;
$hexHeight: 130px;
$gapWidth: 10px;
.container{
  margin: 0 auto;
  font-size: 0;
  width: 768px;
}
// 此处为1行最多显示5个 定义为x
// 那么nth-child 公式为 .hex:nth-child((x * 2)n + (x + 1))
.hex:nth-child(10n + 6){
  margin-left: ($hexWidth / 2) + ( $gapWidth / 2) + $gapWidth;
}
.hex {
  display: inline-block;
  position: relative;
  width: $hexWidth;
  height: $hexHeight;
  margin-left: $gapWidth;
  background: #64c7cc;
  -webkit-clip-path: polygon(0 25%,50% 0,100% 25%,100% 75%,50% 100%,0 75%);
  clip-path: polygon(0 25%,50% 0,100% 25%,100% 75%,50% 100%,0 75%);
}
```

![jICfglGZ7pvJnUt](https://i.loli.net/2020/04/16/jICfglGZ7pvJnUt.png)

### 调整行间距

```scss
$hexWidth: 120px;
$hexHeight: 130px;
$gapWidth: 10px;

.container{
  margin: 0 auto;
  font-size: 0;
  width: 768px;
}
.hex:nth-child(10n + 6){
  margin-left: ($hexWidth / 2) + ( $gapWidth / 2) + $gapWidth;
}
.hex {
  display: inline-block;
  position: relative;
  width: $hexWidth;
  height: $hexHeight;
  margin-left: $gapWidth;
  margin-bottom: -$hexHeight / 4 + $gapWidth;
  background: #64c7cc;
  -webkit-clip-path: polygon(0 25%,50% 0,100% 25%,100% 75%,50% 100%,0 75%);
  clip-path: polygon(0 25%,50% 0,100% 25%,100% 75%,50% 100%,0 75%);
}
```

![U3nq9XNcCADzGIu](https://i.loli.net/2020/04/16/U3nq9XNcCADzGIu.png)

### 实现边框

```scss
$hexWidth: 120px;
$hexHeight: 130px;
$gapWidth: 10px;

.container{
  margin: 0 auto;
  font-size: 0;
  width: 768px;
}
.hex:nth-child(10n + 6){
  margin-left: ($hexWidth / 2) + ( $gapWidth / 2) + $gapWidth;
}
.hex {
  display: inline-block;
  position: relative;
  width: $hexWidth;
  height: $hexHeight;
  margin-left: $gapWidth;
  margin-bottom: -$hexHeight / 4 + $gapWidth;
  background: #64c7cc;
}
.hex::before {
  content: "";
  background-color: #fff;
  left: 2px;
  top: 2px;
  right: 2px;
  bottom: 2px;
  position: absolute;
  z-index: -1;
}
.hex, .hex::before {
  -webkit-clip-path: polygon(0 25%,50% 0,100% 25%,100% 75%,50% 100%,0 75%);
  clip-path: polygon(0 25%,50% 0,100% 25%,100% 75%,50% 100%,0 75%);
}
```

![FkSf5EKXPqzRD4H](https://i.loli.net/2020/04/16/FkSf5EKXPqzRD4H.png)

### 填字

```html
<div class="container">
  <div class="hex">
    <div class="hex-body">
      TEST1
    </div>
  </div>
  <div class="hex">
    <div class="hex-body">
      TEST2
    </div>
  </div>
  <div class="hex">
    <div class="hex-body">
      TEST3
    </div>
  </div>
  <div class="hex">
    <div class="hex-body">
      TEST4
    </div>
  </div>
  <div class="hex">
    <div class="hex-body">
      TEST
    </div>
  </div>
  <div class="hex">
    <div class="hex-body">
      TEST
    </div>
  </div>
  <div class="hex">
    <div class="hex-body">
      TEST5
    </div>
  </div>
  <div class="hex">
    <div class="hex-body">
      TEST6
    </div>
  </div>
  <div class="hex">
    <div class="hex-body">
      TEST7
    </div>
  </div>
  <div class="hex">
    <div class="hex-body">
      TEST8
    </div>
  </div>
  <div class="hex">
    <div class="hex-body">
      TEST9
    </div>
  </div>
  <div class="hex">
    <div class="hex-body">
      TEST10
    </div>
  </div>
  <div class="hex">
    <div class="hex-body">
      TEST11
    </div>
  </div>
  <div class="hex">
    <div class="hex-body">
      TEST12
    </div>
  </div>
  <div class="hex">
    <div class="hex-body">
      TEST13
    </div>
  </div>
   <div class="hex">
    <div class="hex-body">
      TEST14
    </div>
  </div>
   <div class="hex">
    <div class="hex-body">
      TEST15
    </div>
  </div>
   <div class="hex">
    <div class="hex-body">
      TEST16
    </div>
  </div>
   <div class="hex">
    <div class="hex-body">
      TEST17
    </div>
  </div>
   <div class="hex">
    <div class="hex-body">
      TEST18
    </div>
  </div>
</div>
```

```scss
.hex-body {
  height: $hexHeight / 2;
  width: 100%;
  position: absolute;
  left: 0;
  top: 50%;
  transform: translateY(-50%);
  font-size: 16px;
  text-align: center;
}
```

![JEwiRK.png](https://s1.ax1x.com/2020/04/17/JEwiRK.png)

## 响应式调整

> 这边使用 `CSS3` 的 [Media queries](https://developer.mozilla.org/zh-CN/docs/Web/Guide/CSS/Media_queries) 来进行适配，定义几个断点，我们参考[Bootstrap](https://getbootstrap.com/docs/4.4/layout/overview/#containers)的定义：

+ **Extra small**：**< 576px**
+ **Small**: **≥576px**
+ **Medium**: **≥768px**
+ **Large**: **≥992px**
+ **Extra large**: **≥1200px**

```scss
.container{
  margin: 0 auto;
  font-size: 0;
}
/*
Extra large
≥1200px
*/
@media only screen and (min-width : 1200px) {
  .container{
    width: 1140px;
  
  }
  .hex:nth-child(16n + 9){
    margin-left: ($hexWidth / 2) + ( $gapWidth / 2) + $gapWidth;
  }
}
/*
Large
≥992px
*/
@media only screen and (min-width : 992px) and (max-width: 1200px) {
  .container{
    width: 900px;
  
  }
  .hex:nth-child(12n + 7){
    margin-left: ($hexWidth / 2) + ( $gapWidth / 2) + $gapWidth;
  }
}

/*
Medium
≥768px
*/
@media only screen and (min-width : 768px) and (max-width: 992px) {
  .container{
    width: 720px;
  
  }
  .hex:nth-child(10n + 6){
    margin-left: ($hexWidth / 2) + ( $gapWidth / 2) + $gapWidth;
  }
}

/*
Small
≥576px
*/
@media only screen and (min-width : 576px) and (max-width: 768px) {
  .container{
    width: 520px;
  
  }
  .hex:nth-child(6n + 4){
    margin-left: ($hexWidth / 2) + ( $gapWidth / 2) + $gapWidth;
  }
}


/*
Extra small
<576px
*/
@media only screen and (max-width: 575px) {
  .container{
    width: 360px;
  
  }
  .hex:nth-child(4n + 3){
    margin-left: ($hexWidth / 2) + ( $gapWidth / 2) + $gapWidth;
  }
}

```

+ **< 576px**

![JEwKit.png](https://s1.ax1x.com/2020/04/17/JEwKit.png)

+  **≥576px**

![JEwlz8.png](https://s1.ax1x.com/2020/04/17/JEwlz8.png)

+ **≥768px**

![JEwYZj.png](https://s1.ax1x.com/2020/04/17/JEwYZj.png)

+ **≥992px**

![JEwdJ0.png](https://s1.ax1x.com/2020/04/17/JEwdJ0.png)

+ **≥1200px**

![JEwcw9.png](https://s1.ax1x.com/2020/04/17/JEwcw9.png)



## CodePen 链接

<p class="codepen" data-height="576" data-theme-id="dark" data-default-tab="result" data-user="shmy" data-slug-hash="xxwZeNE" style="height: 576px; box-sizing: border-box; display: flex; align-items: center; justify-content: center; border: 2px solid; margin: 1em 0; padding: 1em;" data-pen-title="css-hexagon-layout-item">
  <span>See the Pen <a href="https://codepen.io/shmy/pen/xxwZeNE">
  css-hexagon-layout-item</a> by shmy (<a href="https://codepen.io/shmy">@shmy</a>)
  on <a href="https://codepen.io">CodePen</a>.</span>
</p>
<script async src="https://static.codepen.io/assets/embed/ei.js"></script>