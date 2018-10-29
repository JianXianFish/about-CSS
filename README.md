## 目录
* #### [开发规范](#开发规范-1)
* #### [开发注意事项](#开发注意事项-1)
* #### [HTML <head>](#html-head-1)
* #### [CSS相关](#css相关-1)
  1. [编写CSS规范](#1编写css规范)
  2. [单行溢出省略号](#2单行溢出省略号)
  3. [多行溢出省略号](#3多行溢出省略号)
  4. [placeholder样式](#4placeholder样式)
  5. [渐变](#5渐变)
  6. [flex页脚置底(兼容至ie10)](#6flex页脚置底兼容至ie10)
  7. [css三角形](#7css三角形)
  8. [tab常用响应式不转行，可左右拉动](#8tab常用响应式不转行可左右拉动)
  9. [让背景图随DIV变化，且不变形居中](#9让背景图随div变化且不变形居中)
  10. [重置样式](#10重置样式)
  11. [div内容垂直布局](#11div垂直布局)
  12. [input框在ios中的内阴影问题](#12input框在ios中的内阴影问题)
  13. [去掉ios下可点元素的灰色块](#13去掉ios下可点元素的灰色块)
  14. [flex制作栅格布局](#14flex制作栅格布局)
  ## 开发规范
> 不管有多少人共同参与同一项目，一定要确保每一行代码都像是同一个人编写的。    
[编码规范传送门](http://codeguide.bootcss.com/)

## 开发注意事项

1、插件的版本是否统一；

2、全局样式用谁的；

3、样式表的结构是不是继承的写法，会不会互相干扰；

4、样式优先级如下：    
` 通用选择器 * < 元素(类型)选择器 < 类选择器 < 属性选择器 < 伪类 < ID 选择器 < 内联样式 `

5、团队协作下使用git了吗；

6、不同团队开发，在关于复用的组件以及全局的变量是否有进行沟通；

7、如非特殊情况，慎用!important，因为使用!important会扰乱原本层叠和权重产生正常的作用顺序，使后期维护带来麻烦；

8、链接加title，图标加alt，logo要用h1包裹！

9、一排的展示布局优先使用swiper，否则后面说要加滑动功能就麻烦一些，不如直接用swiper然后不初始化就行了！


## HTML head
```
<meta charset="UTF-8">
<!-- 设置文档宽度、是否缩放 -->
<meta name="viewport" content="width=device-width, user-scalable=no, initial-scale=1.0, maximum-scale=1.0, minimum-scale=1.0">
<!-- 优先使用IE最新版本和Chrome -->
<meta http-equiv="X-UA-Compatible" content="IE=edge,chrome=1" />
<title></title>
<!-- 关键字 -->
<meta name="keywords" content="">
<!-- 描述 -->
<meta name="description" content="">
<!--[if lt IE 9]>
<script src="https://cdn.staticfile.org/html5shiv/r29/html5.min.js"></script>
<script src="https://cdn.staticfile.org/respond.js/1.4.2/respond.min.js"></script>
<![endif]-->
<!--[if lte IE 8]>
<p style="background:#000;text-align: center;color:#fff;font-size: 16px; line-height: 25px;">你的浏览器太老了，请到<a href="http://browsehappy.com" style="color:#ddd">这里</a>更新，以获取最佳的体验</p>
<![endif]-->
<!--[if lte IE 7]>
<p style="background:#000;text-align: center;color:#fff;font-size: 16px; line-height: 25px;">你的浏览器太老了，请到<a href="http://browsehappy.com" style="color:#ddd">这里</a>更新，以获取最佳的体验</p>
<![endif]-->
<!--[if lte IE 6]>
<p style="background:#000;text-align: center;color:#fff;font-size: 16px; line-height: 25px;">你的浏览器太老了，请到<a href="http://browsehappy.com" style="color:#ddd">这里</a>更新，以获取最佳的体验</p>
<![endif]-->
<!-- 360使用Google Chrome Frame -->
<meta name="renderer" content="webkit">
<!-- 百度禁止转码 -->
<meta http-equiv="Cache-Control" content="no-siteapp">
<!-- 定义网页搜索引擎索引方式 -->
<meta name="robots" content="index,follow">
<!-- ios设备 -->
<!-- 添加到主屏后的标题 -->
<meta name="apple-mobile-web-app-title" content="">
<!-- 是否启用WebApp全屏模式 -->
<meta content="yes" name="apple-mobile-web-app-capable">
<meta content="yes" name="apple-touch-fullscreen">
<!-- 设置状态栏的背景颜色 -->
<meta name="apple-mobile-web-app-status-bar-style" content="black-translucent">
<!-- Android theme-color用来控制选项卡颜色。 -->
<meta name="theme-color" content="#747474">
<meta name="mobile-web-app-capable" content="yes">
<!-- 关闭chrome浏览器下翻译插件 -->
<meta name="google" value="notranslate" />
<!-- uc强制竖屏 -->
<meta name="screen-orientation" content="portrait">
<!-- QQ强制竖屏 -->
<meta name="x5-orientation" content="portrait">
<!-- UC强制全屏 -->
<meta name="full-screen" content="yes">
<!-- QQ强制全屏 -->
<meta name="x5-fullscreen" content="true">
<!-- UC应用模式 -->
<meta name="browsermode" content="application">
<!-- QQ应用模式 -->
<meta name="x5-page-mode" content="app">
```

## CSS相关
### 1、编写CSS规范
一个项目不可能从头到尾都是你一个人在开发，哪怕是一个很小的项目，如果每个人都把规范做到极致，所有事情都会变得更简单。在我遇到的大部分开发中，用Git合并项目时，遇到最多的冲突就是样式表用来用去不知道在用谁的，改来改去还不好改；如果我们把样式拆分成模块会方便很多，这样出了问题一看就知道是谁的锅了，譬如在用Less的时候：

![Less目录](https://raw.githubusercontent.com/ZHAO-Shaofeng/Related-considerations-for-HTML-CSS-JS/master/github-img/mulu.png)

这样的目录一目了然哪个文件是哪个部分的

将经常用到的样式单独定义写到_variable.less里

![全局变量](https://raw.githubusercontent.com/ZHAO-Shaofeng/Related-considerations-for-HTML-CSS-JS/master/github-img/variable.png)

然后再把所有的文件引入到style.less

![整合less](https://raw.githubusercontent.com/ZHAO-Shaofeng/Related-considerations-for-HTML-CSS-JS/master/github-img/style.png)

哪怕你是用的原生css来写，如果在class上写明哪个文件并添加注释之后，不觉得这样看起来更清晰吗

![原生css](https://raw.githubusercontent.com/ZHAO-Shaofeng/Related-considerations-for-HTML-CSS-JS/master/github-img/css.png)

只是用Less举个例子想把规范说清楚，至于用原生css还是用css的预编译处理语言这里不作讨论

但是显然用预编译处理语言在开发和贴近规范上会更方便一些，这是推荐使用的。    
如果我们的样式表都是通过嵌套规则来一个个继承的，不管你用哪个都不会有任何冲突，因为彼此之间的关系是很清晰的。

### 2、单行溢出省略号
```
overflow: hidden;
text-overflow: ellipsis;
white-space: nowrap;
```

### 3、多行溢出省略号
```
overflow : hidden;
text-overflow: ellipsis;
display: -webkit-box;
-webkit-line-clamp: 2;
-webkit-box-orient: vertical;
```

### 4、placeholder样式
```
input::-webkit-input-placeholder{
  color:red;
}
input::-moz-placeholder{
  color:red;
}
input:-moz-placeholder{
  color:red;
}
input:-ms-input-placeholder{
  color:red;
}
```
 
### 5、渐变
*  从上到下
```
background: -webkit-linear-gradient(red, blue);
background: -o-linear-gradient(red, blue);
background: -moz-linear-gradient(red, blue);
background: linear-gradient(red, blue);
```
 
*  从左到右
```
background: linear-gradient(to right, red , blue);
```
 
*  角度
```
background: linear-gradient(to bottom right, red , blue);  /*左上角至右下角*/
background: linear-gradient(180deg, red, blue);  /*指定角度*/
```
 
*  多个颜色
```
background: linear-gradient(red, green, blue);
```
 
### 6、flex页脚置底(兼容至ie10)
```
<body>
    <header></header>
    <main></main>
    <footer></footer>
</body>

html{height: 100%;}
body{
	height: 100%;
	min-height: 100%;
	display: flex;
	flex-direction: column;
}
.main{
	flex: 1 0 auto;
}
.footer{
	flex: 0 0 auto;
}
```

### 7、css三角形
[传送门](http://www.jb51.net/article/42513.htm)

### 8、tab常用响应式不转行，可左右拉动
放在容器里的样式
```
white-space: nowrap;
overflow-x: auto;
display: flex;
overflow-y: hidden;
```

### 9、让背景图随DIV变化，且不变形居中
让背景图随DIV变化，且不变形居中。
```
background-image: url("../images/index/banner.png");
background-repeat: no-repeat;
background-size: cover;
background-attachment: fixed;
background-position: center center;
```

### 10、重置样式
参考网站：https://meyerweb.com/eric/tools/css/reset/index.html
```
/* http://meyerweb.com/eric/tools/css/reset/ 
   v2.0 | 20110126
   License: none (public domain)
*/

html, body, div, span, applet, object, iframe,
h1, h2, h3, h4, h5, h6, p, blockquote, pre,
a, abbr, acronym, address, big, cite, code,
del, dfn, em, img, ins, kbd, q, s, samp,
small, strike, strong, sub, sup, tt, var,
b, u, i, center,
dl, dt, dd, ol, ul, li,
fieldset, form, label, legend,
table, caption, tbody, tfoot, thead, tr, th, td,
article, aside, canvas, details, embed, 
figure, figcaption, footer, header, hgroup, 
menu, nav, output, ruby, section, summary,
time, mark, audio, video {
	margin: 0;
	padding: 0;
	border: 0;
	font-size: 100%;
	font: inherit;
	vertical-align: baseline;
}
/* HTML5 display-role reset for older browsers */
article, aside, details, figcaption, figure, 
footer, header, hgroup, menu, nav, section {
	display: block;
}
body {
	line-height: 1;
}
ol, ul {
	list-style: none;
}
blockquote, q {
	quotes: none;
}
blockquote:before, blockquote:after,
q:before, q:after {
	content: '';
	content: none;
}
table {
	border-collapse: collapse;
	border-spacing: 0;
}
```

### 11、div垂直布局
```
display: table-cell;
vertical-align: middle;
```

### 12、input框在ios下的内阴影问题
```
-webkit-appearance: none;
```

### 13、去掉ios下可点元素的灰色块
```
-webkit-tap-highlight-color: transparent;
```

### 14、flex制作栅格布局
```
flexbox
┌─────────────────────────────┐
│                             │
│  box-row                    │
│ ┌─────────────────────────┐ │
│ │                         │ │
│ │ box-col                 │ │
│ │ ┌───┐ ┌───┐ ┌───┐ ┌───┐ │ │
│ │ │ 3 │ │ 3 │ │ 3 │ │ 3 │ │ │
│ │ └───┘ └───┘ └───┘ └───┘ │ │
│ └─────────────────────────┘ │
└─────────────────────────────┘

<div class="flexbox">
  <div class="box-row">
    <div class="box-col"> 3 </div>
    <div class="box-col"> 3 </div>
    <div class="box-col"> 3 </div>
    <div class="box-col"> 3 </div>
  </div>
</div>

.flexbox{
  overflow: hidden;

  .box-row{
    margin: 0 -10px;
    display: flex;
    flex-wrap: wrap;
    // align-items: flex-start;
  }

  .box-col{
    flex: 0 0 25%;
    min-width: 25%;
    padding: 0 10px;
    margin: 0 0 15px;
  }
}
```
