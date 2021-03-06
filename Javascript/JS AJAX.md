* [JS AJAX](#js-ajax)
	* [AJAX 简介](#ajax-简介)
		* [什么是 AJAX？](#什么是-ajax)
		* [AJAX 如何工作](#ajax-如何工作)
	* [AJAX - XMLHttpRequest 对象](#ajax-xmlhttprequest-对象)
		* [XMLHttpRequest 对象](#xmlhttprequest-对象)
		* [创建 XMLHttpRequest 对象](#创建-xmlhttprequest-对象)
		* [跨域访问](#跨域访问)
		* [XMLHttpRequest 对象方法](#xmlhttprequest-对象方法)
		* [XMLHttpRequest 对象属性](#xmlhttprequest-对象属性)
	* [AJAX - 向服务器发送请求](#ajax-向服务器发送请求)
		* [向服务器发送请求](#向服务器发送请求)
		* [GET 还是 POST？](#get-还是-post)
		* [GET 请求](#get-请求)
		* [POST 请求](#post-请求)
		* [url - 服务器上的文件](#url-服务器上的文件)
		* [异步 - ture 还是 false？](#异步-ture-还是-false)
		* [onreadystatechange 属性](#onreadystatechange-属性)
		* [同步请求](#同步请求)
	* [AJAX - 服务器响应](#ajax-服务器响应)
		* [onreadystatechange 属性](#onreadystatechange-属性)
		* [使用回调函数](#使用回调函数)
		* [服务器响应属性](#服务器响应属性)
		* [服务器响应方法](#服务器响应方法)
		* [responseText 属性](#responsetext-属性)
		* [responseXML 属性](#responsexml-属性)
		* [getAllResponseHeaders() 方法](#getallresponseheaders-方法)
		* [getResponseHeader() 方法](#getresponseheader-方法)
	* [AJAX PHP 实例](#ajax-php-实例)
	* [AJAX ASP 实例](#ajax-asp-实例)
	* [AJAX Database 实例](#ajax-database-实例)
	* [AJAX XML 应用程序](#ajax-xml-应用程序)
	* [AJAX 实例](#ajax-实例)

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

![方法](https://raw.githubusercontent.com/Grekevin/development-manual-imgs/master/1611060944375.png)

### XMLHttpRequest 对象属性

![属性](https://raw.githubusercontent.com/Grekevin/development-manual-imgs/master/1611061001736.png)

## AJAX - 向服务器发送请求

> XMLHttpRequest 对象用于同服务器交换数据。

### 向服务器发送请求

如需向服务器发送请求，我们使用 XMLHttpRequest 对象的 open() 和 send() 方法：

``` javascript
xhttp.open("GET", "ajax_info.txt", true);
xhttp.send();
```

![发送请求](https://raw.githubusercontent.com/Grekevin/development-manual-imgs/master/1611061395249.png)

### GET 还是 POST？

GET 比 POST 更简单更快，可用于大多数情况下。

不过，请在以下情况始终使用 POST：

 - 缓存文件（更新服务器上的文件或数据库）
 - 向服务器发送大量数据（POST 无大小限制）
 - 发送用户输入（可包含未知字符），POST 比 GET 更强大更安全

### GET 请求

一条简单的 GET 请求：

``` javascript
xhttp.open("GET", "demo_get.asp", true);
xhttp.send();
```

在上面的例子中，您可能会获得一个缓存的结果。为了避免此情况，请向 URL 添加一个唯一的 ID：

``` javascript
xhttp.open("GET", "demo_get.asp?t=" + Math.random(), true);
xhttp.send();
```

如果您需要用 GET 方法来发送信息，请向 URL 添加这些信息：

``` javascript
xhttp.open("GET", "demo_get2.asp?fname=Bill&lname=Gates", true);
xhttp.send();
```

### POST 请求

一条简单的 POST 请求：

``` javascript
xhttp.open("POST", "demo_post.asp", true);
xhttp.send();
```

如需像 HTML 表单那样 POST 数据，请通过 setRequestHeader() 添加一个 HTTP 头部。请在 send() 方法中规定您需要发送的数据：

``` javascript
xhttp.open("POST", "ajax_test.asp", true);
xhttp.setRequestHeader("Content-type", "application/x-www-form-urlencoded");
xhttp.send("fname=Bill&lname=Gates");
```
![setRequestHeader](https://raw.githubusercontent.com/Grekevin/development-manual-imgs/master/1611125190822.png)

### url - 服务器上的文件

open() 方法的 url 参数，是服务器上文件的地址：

``` javascript
xhttp.open("GET", "ajax_test.asp", true);
```

该文件可以是任何类型的文件，如 .txt 和 .xml，或服务器脚本文件，如 .asp 和 .php（它们可以在发送回响应之前在服务器执行操作）。


### 异步 - ture 还是 false？

如需异步发送请求，open() 方法的 async 参数必须设置为 true：

``` javascript
xhttp.open("GET", "ajax_test.asp", true);
```

发送异步请求对 web 开发人员来说是一个巨大的进步。服务器上执行的许多任务都非常耗时。在 AJAX 之前，此操作可能会导致应用程序挂起或停止。

通过异步发送，JavaScript 不必等待服务器响应，而是可以：

 - 在等待服务器响应时执行其他脚本
 - 当响应就绪时处理响应

### onreadystatechange 属性

通过 XMLHttpRequest 对象，您可以定义当请求接收到应答时所执行的函数。

这个函数是在 XMLHttpResponse 对象的 onreadystatechange 属性中定义的：

``` javascript
xhttp.onreadystatechange = function() {
  if (this.readyState == 4 && this.status == 200) {
    document.getElementById("demo").innerHTML = this.responseText;
  }
};
xhttp.open("GET", "ajax_info.txt", true);
xhttp.send();
```

### 同步请求

如需执行同步的请求，请把 open() 方法中的第三个参数设置为 false：

``` javascript
xhttp.open("GET", "ajax_info.txt", false);
```

有时 async = false 用于快速测试。你也会在更老的 JavaScript 代码中看到同步请求。

由于代码将等待服务器完成，所以不需要 onreadystatechange 函数：

``` javascript
xhttp.open("GET", "ajax_info.txt", false);
xhttp.send();
document.getElementById("demo").innerHTML = xhttp.responseText;
```

我们不推荐同步的 XMLHttpRequest (async = false)，因为 JavaScript 将停止执行直到服务器响应就绪。如果服务器繁忙或缓慢，应用程序将挂起或停止。

同步 XMLHttpRequest 正在从 Web 标准中移除，但是这个过程可能需要很多年。

现代开发工具被鼓励对使用同步请求做出警告，并且当这种情况发生时，可能会抛出 InvalidAccessError 异常。

## AJAX - 服务器响应

### onreadystatechange 属性

`readyState` 属性保存 `XMLHttpRequest` 的状态。

`onreadystatechange` 属性定义当 `readyState` 发生变化时执行的函数。

`status` 属性和 `statusText` 属性存有 `XMLHttpRequest` 对象的状态。

![enter description here](https://raw.githubusercontent.com/Grekevin/development-manual-imgs/master/1611125878237.png)

每当 `readyState` 发生变化时就会调用 `onreadystatechange` 函数。

当 `readyState` 为 4，`status` 为 200 时，响应就绪：

``` javascript
function loadDoc() {
    var xhttp = new XMLHttpRequest();
    xhttp.onreadystatechange = function() {
        if (this.readyState == 4 && this.status == 200) {
            document.getElementById("demo").innerHTML =
            this.responseText;
       }
    };
    xhttp.open("GET", "ajax_info.txt", true);
    xhttp.send(); 
} 
```

> 注释：onreadystatechange 被触发五次（0-4），每次 readyState 都发生变化。

### 使用回调函数

回调函数是一种作为参数被传递到另一个函数的函数。

如果您的网站中有多个 AJAX 任务，那么您应该创建一个执行 XMLHttpRequest 对象的函数，以及一个供每个 AJAX 任务的回调函数。

该函数应当包含 URL 以及当响应就绪时调用的函数。

``` html
<!DOCTYPE html>
<html>
<body>

<div id="demo">

<h1>XMLHttpRequest 对象</h1>

<button type="button" onclick="loadDoc('/example/js/ajax_info.txt', myFunction)">更改内容
</button>
</div>

<script>
function loadDoc(url, cFunction) {
  var xhttp;
  xhttp=new XMLHttpRequest();
  xhttp.onreadystatechange = function() {
    if (this.readyState == 4 && this.status == 200) {
      cFunction(this);
    }
  };
  xhttp.open("GET", url, true);
  xhttp.send();
}
function myFunction(xhttp) {
  document.getElementById("demo").innerHTML =
  xhttp.responseText;
}
</script>
</body>
</html>
```

### 服务器响应属性

| 属性 | 描述 |
| --- | --- |
| responseText | 获取字符串形式的响应数据 |
| responseXML | 获取 XML 数据形式的响应数据 |

### 服务器响应方法

| 方法 | 描述 |
| --- | --- |
| getResponseHeader() | 从服务器返回特定的头部信息 |
| getAllResponseHeaders() | 从服务器返回所有头部信息 |

### responseText 属性

responseText 属性以 JavaScript 字符串的形式返回服务器响应，因此您可以这样使用它：

``` javascript
document.getElementById("demo").innerHTML = xhttp.responseText;
```

### responseXML 属性

XML HttpRequest 对象有一个內建的 XML 解析器。

ResponseXML 属性以 XML DOM 对象返回服务器响应。

使用此属性，您可以把响应解析为 XML DOM 对象：

[responseXML示例](https://www.w3school.com.cn/js/js_ajax_http_response.asp)

[AJAX XML 实例](https://www.w3school.com.cn/js/js_ajax_xmlfile.asp)

### getAllResponseHeaders() 方法

getAllResponseHeaders() 方法返回所有来自服务器响应的头部信息。

``` javascript
var xhttp = new XMLHttpRequest();
xhttp.onreadystatechange = function() {
  if (this.readyState == 4 && this.status == 200) {
    document.getElementById("demo").innerHTML = this.getAllResponseHeaders();
  }
};
```

### getResponseHeader() 方法

getResponseHeader() 方法返回来自服务器响应的特定头部信息。

``` javascript
var xhttp = new XMLHttpRequest();
xhttp.onreadystatechange = function() {
  if (this.readyState == 4 && this.status == 200) {
    document.getElementById("demo").innerHTML = this.getResponseHeader("Last-Modified");
  }
};
xhttp.open("GET", "ajax_info.txt", true);
xhttp.send(); 
```

## [AJAX PHP 实例](https://www.w3school.com.cn/js/js_ajax_php.asp)

## [AJAX ASP 实例](https://www.w3school.com.cn/js/js_ajax_asp.asp)

## [AJAX Database 实例](https://www.w3school.com.cn/js/js_ajax_database.asp)

## [AJAX XML 应用程序](https://www.w3school.com.cn/js/js_ajax_applications.asp)

## [AJAX 实例](https://www.w3school.com.cn/js/js_ajax_examples.asp)