#  JS Browser BOM
## JavaScript Window - 浏览器对象模型

> 浏览器对象模型（Browser Object Model (BOM)）允许 JavaScript 与浏览器对话。

### 浏览器对象模型（Browser Object Model (BOM)）

不存在浏览器对象模型（BOM）的官方标准。

现代的浏览器已经（几乎）实现了 JavaScript 交互相同的方法和属性，因此它经常作为 BOM 的方法和属性被提到。

### Window 对象

所有浏览器都支持 window 对象。它代表浏览器的窗口。

所有全局 JavaScript 对象，函数和变量自动成为 window 对象的成员。

全局变量是 window 对象的属性。

全局函数是 window 对象的方法。

甚至（HTML DOM 的）document 对象也是 window 对象属性：

``` javascript
window.document.getElementById("header");
//等同于：
document.getElementById("header");
```

### 窗口尺寸

两个属性可用用于确定浏览器窗口的尺寸。

这两个属性都以像素返回尺寸：

``` javascript
window.innerHeight - 浏览器窗口的内高度（以像素计）
window.innerWidth - 浏览器窗口的内宽度（以像素计）
```

浏览器窗口（浏览器视口）不包括工具栏和滚动条。

对于 Internet Explorer 8, 7, 6, 5：

``` javascript
document.documentElement.clientHeight
document.documentElement.clientWidth
//或
document.body.clientHeight
document.body.clientWidth
```

一个实用的 JavaScript 解决方案（包括所有浏览器）：

``` javascript
var w = window.innerWidth
|| document.documentElement.clientWidth
|| document.body.clientWidth;

var h = window.innerHeight
|| document.documentElement.clientHeight
|| document.body.clientHeight; 
```

### 其他窗口方法

一些其他方法：

 - window.open() - 打开新窗口
 - window.close() - 关闭当前窗口
 - window.moveTo() -移动当前窗口
 - window.resizeTo() -重新调整当前窗口

## JavaScript Window Screen

> window.screen 对象包含用户屏幕的信息。

### Window Screen

window.screen 对象不带 window 前缀也可以写：

属性：

 - screen.width (返回以像素计的访问者屏幕宽度)
 - screen.height (返回以像素计的访问者屏幕的高度)
 - screen.availWidth (返回访问者屏幕的宽度，以像素计，减去诸如窗口工具条之类的界面特征)
 - screen.availHeight (返回访问者屏幕的高度，以像素计，减去诸如窗口工具条之类的界面特征)
 - screen.colorDepth 
 - screen.pixelDepth (返回屏幕的像素深度,对于现代计算机，颜色深度和像素深度是相等的。)

### Window Screen 色深

screen.colorDepth 属性返回用于显示一种颜色的比特数。

所有现代计算机都使用 24 位或 32 位硬件的色彩分辨率：

 - 24 bits =16,777,216 种不同的 "True Colors"
 - 32 bits = 4,294,967,296 中不同的 "Deep Colors"

更老的计算机使用 14 位：65,536 种不同的 "High Colors" 分辨率。

异常古老的计算机，以及老式的手机使用 8 位：256 中不同的 "VGA colors"。

显示以位计的屏幕色彩深度：

``` javascript
document.getElementById("demo").innerHTML = "Screen Color Depth: " + screen.colorDepth;
```

结果将是：

``` javascript
Screen Color Depth: 24
```

> HTML 中使用的 #rrggbb (rgb) 值代表 "True Colors" （16,777,216 中不同的颜色）。

## JavaScript Window Location

> window.location 对象可用于获取当前页面地址（URL）并把浏览器重定向到新页面。

### Window Location

window.location 对象可不带 window 前缀书写。

一些例子：

 - window.location.href 返回当前页面的 href (URL)
 - window.location.hostname 返回（当前页面的）因特网主机的名称
 - window.location.pathname 返回当前页面的路径或文件名
 - window.location.protocol 返回使用的 web 协议（http: 或 https:）
 - window.location.assign 加载新文档
 - window.location.port 属性返回（当前页面的）互联网主机端口的编号。大多数浏览器不会显示默认端口号（http 为 80，https 为 443）。

## JavaScript Window History

> window.history 对象包含浏览器历史。

### Window History

window.history 对象可不带 window 书写。

为了保护用户的隐私，JavaScript 访问此对象存在限制。

一些方法：

 - history.back() - 等同于在浏览器点击后退按钮(加载历史列表中前一个 URL)
 - history.forward() - 等同于在浏览器中点击前进按钮(加载历史列表中下一个 URL)

### Window History Back

history.back() 方法加载历史列表中前一个 URL。

这等同于在浏览器中点击后退按钮。

在页面中创建后退按钮：

``` html
<html>
<head>
<script>
function goBack() {
    window.history.back()
 }
</script>
</head>
<body>

<input type="button" value="Back" onclick="goBack()">

</body>
</html>
```

## JavaScript Window Navigator

> window.navigator 对象包含有关访问者的信息。

### Window Navigator

window.navigator 对象可以不带 window 前缀来写。

一些例子：

 - navigator.appName (返回浏览器的应用程序名称)
   "Netscape" 是 IE11、Chrome、Firefox 以及 Safari 的应用程序名称的统称。
 - navigator.appCodeName (返回浏览器的应用程序代码名称)
   "Mozilla" 是 Chrome、Firefox、IE、Safari 以及 Opera 的应用程序代码名称。
 - navigator.platform

### 浏览器 Cookie

cookieEnabled 属性返回 true，如果 cookie 已启用，否则返回 false：

``` html
<p id="demo"></p>

<script>
document.getElementById("demo").innerHTML = "cookiesEnabled is " + navigator.cookieEnabled;
</script>
```

### 浏览器引擎

product 属性返回浏览器引擎的产品名称：

``` html
<p id="demo"></p>

<script>
document.getElementById("demo").innerHTML = "navigator.product is " + navigator.product;
</script>
```
> 不要依赖它！大多数浏览器都将 “Gecko” 作为产品名称返回！

### 浏览器版本

appVersion 属性返回有关浏览器的版本信息：

``` html
<p id="demo"></p>

<script>
//5.0 (Windows NT 6.1; Win64; x64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/87.0.4280.141 Safari/537.36
document.getElementById("demo").innerHTML = navigator.appVersion;
</script>
```

### 浏览器代理

userAgent 属性返回由浏览器发送到服务器的用户代理报头（user-agent header）：

``` html
<p id="demo"></p>

<script>
//Mozilla/5.0 (Windows NT 6.1; Win64; x64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/87.0.4280.141 Safari/537.36
document.getElementById("demo").innerHTML = navigator.userAgent;
</script>
```
### 警告！！！

来自 navigator 对象的信息通常是误导性的，不应该用于检测浏览器版本，因为：

 - 不同浏览器能够使用相同名称
 - 导航数据可被浏览器拥有者更改
 - 某些浏览器会错误标识自身以绕过站点测试
 - 浏览器无法报告发布晚于浏览器的新操作系统

### 浏览器平台

platform 属性返回浏览器平台（操作系统）：

``` html
<p id="demo"></p>

<script>
document.getElementById("demo").innerHTML = navigator.platform;	//Win32
</script>
```

### 浏览器语言

language 属性返回浏览器语言：

``` html
<p id="demo"></p>

<script>
document.getElementById("demo").innerHTML = navigator.language;	//en
</script>
```

### 浏览器是否在线？

onLine 属性返回 true，假如浏览器在线：

``` html
<p id="demo"></p>

<script>
document.getElementById("demo").innerHTML = navigator.onLine;
</script>
```

### Java 是否启用？

javaEnabled() 方法返回 true，如果 Java 已启用：

``` html
<p id="demo"></p>

<script>
document.getElementById("demo").innerHTML = navigator.javaEnabled();
</script>
```

## JavaScript 弹出框

> JavaScript 有三种类型的弹出框：警告框、确认框和提示框。

### 警告框

如果要确保信息传递给用户，通常会使用警告框。

当警告框弹出时，用户将需要单击“确定”来继续。

``` javascript
window.alert("sometext");
```

window.alert() 方法可以不带 window 前缀来写。

``` javascript
alert("我是一个警告框！");
```

### 确认框

如果您希望用户验证或接受某个东西，则通常使用“确认”框。

当确认框弹出时，用户将不得不单击“确定”或“取消”来继续进行。

如果用户单击“确定”，该框返回 true。如果用户单击“取消”，该框返回 false。

``` javascript
window.confirm("sometext");
```

window.confirm() 方法可以不带 window 前缀来编写。

``` javascript
var r = confirm("请按按钮");
if (r == true) {
    x = "您按了确认！";
} else {
    x = "您按了取消！";
}
```

### 提示框

如果您希望用户在进入页面前输入值，通常会使用提示框。

当提示框弹出时，用户将不得不输入值后单击“确定”或点击“取消”来继续进行。

如果用户单击“确定”，该框返回输入值。如果用户单击“取消”，该框返回 NULL。

``` javascript
window.prompt("sometext","defaultText");
```

window.prompt() 方法可以不带 window 前缀来编写。

``` javascript
var person = prompt("请输入您的姓名", "比尔盖茨");
if (person != null) {
    document.getElementById("demo").innerHTML = "你好 " + person + "！今天过的怎么样？";
}
```

### 折行

如需在弹出框中显示折行，请在反斜杠后面加一个字符 n。

``` javascript
alert("Hello\nHow are you?");
```

## JavaScript Timing 事件

> JavaScript 可以在时间间隔内执行。
> 这就是所谓的定时事件（ Timing Events）。

### Timing 事件

window 对象允许以指定的时间间隔执行代码。

这些时间间隔称为定时事件。

通过 JavaScript 使用的有两个关键的方法：

``` javascript
setTimeout(function, milliseconds)
```

在等待指定的毫秒数后执行函数。

``` javascript
setInterval(function, milliseconds)
```

等同于 setTimeout()，但持续重复执行该函数。
setTimeout() 和 setInterval() 都属于 HTML DOM Window 对象的方法。

### setTimeout() 方法

``` javascript
window.setTimeout(function, milliseconds);
```

window.setTimeout() 方法可以不带 window 前缀来编写。

 - 第一个参数是要执行的函数。
 - 第二个参数指示执行之前的毫秒数。

单击按钮。等待 3 秒，然后页面会提示 "Hello"：

``` html
<button onclick="setTimeout(myFunction, 3000)">试一试</button>

<script>
function myFunction() {
    alert('Hello');
 }
</script>
```

### 如何停止执行？

clearTimeout() 方法停止执行 setTimeout() 中规定的函数。

``` javascript
window.clearTimeout(timeoutVariable)
```

window.clearTimeout() 方法可以不带 window 前缀来写。

clearTimeout() 使用从 setTimeout() 返回的变量：

``` javascript
myVar = setTimeout(function, milliseconds);
clearTimeout(myVar);
```