
# JS AJAX

## AJAX 简介

AJAX 是开发者的梦想，因为您能够：

 - 不刷新页面更新网页
 - 在页面加载后从服务器请求数据
 - 在页面加载后从服务器接收数据
 - 在后台向服务器发送数据

AJAX:

 - AJAX 并不是编程语言。
 - AJAX 是一种从网页访问 Web 服务器的技术。
 - AJAX 代表异步 JavaScript 和 XML。

### 什么是 AJAX？

AJAX = Asynchronous JavaScript And XML.

AJAX 并非编程语言。

AJAX 仅仅组合了：

 - 浏览器内建的 XMLHttpRequest 对象（从 web 服务器请求数据）
 - JavaScript 和 HTML DOM（显示或使用数据）

Ajax 是一个令人误导的名称。Ajax 应用程序可能使用 XML 来传输数据，但将数据作为纯文本或 JSON 文本传输也同样常见。

Ajax 允许通过与场景后面的 Web 服务器交换数据来异步更新网页。这意味着可以更新网页的部分，而不需要重新加载整个页面。

### AJAX 如何工作

![AJAX 如何工作](https://raw.githubusercontent.com/Grekevin/development-manual-imgs/master/1611059371722.png)

 1. 网页中发生一个事件（页面加载、按钮点击）
 2. 由 JavaScript 创建 XMLHttpRequest 对象
 3. XMLHttpRequest 对象向 web 服务器发送请求
 4. 服务器处理该请求
 5. 服务器将响应发送回网页
 6. 由 JavaScript 读取响应
 7. 由 JavaScript 执行正确的动作（比如更新页面）

## AJAX - XMLHttpRequest 对象

> Ajax 的核心是 XMLHttpRequest 对象。

### XMLHttpRequest 对象

所有现代浏览器都支持 XMLHttpRequest 对象。

XMLHttpRequest 对象用于同幕后服务器交换数据。这意味着可以更新网页的部分，而不需要重新加载整个页面。

### 创建 XMLHttpRequest 对象

所有现代浏览器（Chrom、IE7+、Firefox、Safari 以及 Opera）都有内建的 XMLHttpRequest 对象。

创建 XMLHttpRequest 的语法是：

``` javascript
variable = new XMLHttpRequest();
```

老版本的 Internet Explorer（IE5 和 IE6）使用 ActiveX 对象：

``` javascript
variable = new ActiveXObject("Microsoft.XMLHTTP");
```

为了应对所有浏览器，包括 IE5 和 IE6，请检查浏览器是否支持 XMLHttpRequest 对象。如果支持，创建 XMLHttpRequest 对象，如果不支持，则创建 ActiveX 对象：

``` javascript
var xhttp;
if (window.XMLHttpRequest) {
    xhttp = new XMLHttpRequest();
    } else {
    // code for IE6, IE5
     xhttp = new ActiveXObject("Microsoft.XMLHTTP");
}
```

### 跨域访问

出于安全原因，现代浏览器不允许跨域访问。

这意味着尝试加载的网页和 XML 文件都必须位于相同服务器上。

W3School 上的实例都会打开位于 W3School 域上的 XML 文件。

如果您希望在自己的页面上使用以上实例，那么您所加载的 XML 文件必须位于您自己的服务器上。

### XMLHttpRequest 对象方法

![方法](https://markdown.xiaoshujiang.com/img/spinner.gif "[[[1611060944376]]]" )

### XMLHttpRequest 对象属性

![属性](https://markdown.xiaoshujiang.com/img/spinner.gif "[[[1611061001737]]]" )

