* [JS HTML DOM](#js-html-dom)
	* [DOM 简介](#dom-简介)
		* [HTML DOM（文档对象模型）](#html-dom文档对象模型)
		* [什么是 DOM？](#什么是-dom)
		* [什么是 HTML DOM？](#什么是-html-dom)
	* [JavaScript - HTML DOM 方法](#javascript-html-dom-方法)
		* [DOM 编程界面](#dom-编程界面)
		* [getElementById 方法](#getelementbyid-方法)
		* [innerHTML 属性](#innerhtml-属性)
	* [JavaScript HTML DOM 文档](#javascript-html-dom-文档)
		* [HTML DOM Document 对象](#html-dom-document-对象)
		* [查找 HTML 元素](#查找-html-元素)
		* [改变 HTML 元素](#改变-html-元素)
		* [添加和删除元素](#添加和删除元素)
		* [添加事件处理程序](#添加事件处理程序)
		* [查找 HTML 对象](#查找-html-对象)
	* [JavaScript HTML DOM 元素](#javascript-html-dom-元素)
		* [查找 HTML 元素](#查找-html-元素)
		* [通过 id 查找 HTML 元素](#通过-id-查找-html-元素)
		* [通过 CSS 选择器查找 HTML 元素](#通过-css-选择器查找-html-元素)
		* [通过 HTML 对象选择器查找 HTML 对象](#通过-html-对象选择器查找-html-对象)
	* [JavaScript HTML DOM - 改变 HTML](#javascript-html-dom-改变-html)
		* [改变 HTML 输出流](#改变-html-输出流)
		* [改变 HTML 内容](#改变-html-内容)
		* [改变属性的值](#改变属性的值)
	* [JavaScript HTML DOM - 改变 CSS](#javascript-html-dom-改变-css)
		* [改变 HTML 样式](#改变-html-样式)
		* [使用事件](#使用事件)
	* [JavaScript HTML DOM 事件](#javascript-html-dom-事件)
		* [对事件作出反应](#对事件作出反应)
		* [HTML 事件属性](#html-事件属性)
		* [使用 HTML DOM 分配事件](#使用-html-dom-分配事件)
		* [onload 和 onunload 事件](#onload-和-onunload-事件)
		* [onchange 事件](#onchange-事件)
		* [onmouseover 和 onmouseout 事件](#onmouseover-和-onmouseout-事件)
		* [onmousedown, onmouseup 以及 onclick 事件](#onmousedown-onmouseup-以及-onclick-事件)
	* [JavaScript HTML DOM 事件监听器](#javascript-html-dom-事件监听器)
		* [addEventListener() 方法](#addeventlistener-方法)
		* [向元素添加事件处理程序](#向元素添加事件处理程序)
		* [向相同元素添加多个事件处理程序](#向相同元素添加多个事件处理程序)
		* [向 Window 对象添加事件处理程序](#向-window-对象添加事件处理程序)
		* [传递参数](#传递参数)
		* [事件冒泡还是事件捕获？](#事件冒泡还是事件捕获)
		* [removeEventListener() 方法](#removeeventlistener-方法)
		* [浏览器支持](#浏览器支持)
	* [JavaScript HTML DOM 导航](#javascript-html-dom-导航)
		* [子节点和节点值](#子节点和节点值)
		* [DOM 根节点](#dom-根节点)
		* [nodeName 属性](#nodename-属性)
		* [nodeValue 属性](#nodevalue-属性)
		* [nodeType 属性](#nodetype-属性)
	* [JavaScript HTML DOM 元素（节点）](#javascript-html-dom-元素节点)
		* [创建新 HTML 元素（节点）](#创建新-html-元素节点)
		* [删除已有 HTML 元素](#删除已有-html-元素)
		* [替换 HTML 元素](#替换-html-元素)
	* [JavaScript HTML DOM 集合](#javascript-html-dom-集合)
		* [HTMLCollection 对象](#htmlcollection-对象)
		* [HTML HTMLCollection 长度](#html-htmlcollection-长度)
		* [HTMLCollection 并非数组！](#htmlcollection-并非数组)
	* [JavaScript HTML DOM 节点列表](#javascript-html-dom-节点列表)
		* [HTML DOM NodeList 对象](#html-dom-nodelist-对象)
		* [HTML DOM Node List 长度](#html-dom-node-list-长度)
		* [HTMLCollection 与 NodeList 的区别](#htmlcollection-与-nodelist-的区别)

#  JS HTML DOM

## DOM 简介

> 通过 HTML DOM，JavaScript 能够访问和改变 HTML 文档的所有元素。

### HTML DOM（文档对象模型）

当网页被加载时，浏览器会创建页面的文档对象模型（Document Object Model）。

HTML DOM 模型被结构化为对象树：

![DOM 树](https://raw.githubusercontent.com/Grekevin/development-manual-imgs/master/1610967589276.png)

通过这个对象模型，JavaScript 获得创建动态 HTML 的所有力量：

 - JavaScript 能改变页面中的所有 HTML 元素
 - JavaScript 能改变页面中的所有 HTML 属性
 - JavaScript 能改变页面中的所有 CSS 样式
 - JavaScript 能删除已有的 HTML 元素和属性
 - JavaScript 能添加新的 HTML 元素和属性
 - JavaScript 能对页面中所有已有的 HTML 事件作出反应
 - JavaScript 能在页面中创建新的 HTML 事件

### 什么是 DOM？

DOM 是一项 W3C (World Wide Web Consortium) 标准。

DOM 定义了访问文档的标准：

“W3C 文档对象模型（DOM）是中立于平台和语言的接口，它允许程序和脚本动态地访问、更新文档的内容、结构和样式。”
W3C DOM 标准被分为 3 个不同的部分：

 - Core DOM - 所有文档类型的标准模型
 - XML DOM - XML 文档的标准模型
 - HTML DOM - HTML 文档的标准模型

### 什么是 HTML DOM？

HTML DOM 是 HTML 的标准对象模型和编程接口。它定义了：

 - 作为对象的 HTML 元素
 - 所有 HTML 元素的属性
 - 访问所有 HTML 元素的方法
 - 所有 HTML 元素的事件

换言之：HTML DOM 是关于如何获取、更改、添加或删除 HTML 元素的标准。

## JavaScript - HTML DOM 方法

> HTML DOM 方法是您能够（在 HTML 元素上）执行的动作。
HTML DOM 属性是您能够设置或改变的 HTML 元素的值。

### DOM 编程界面

HTML DOM 能够通过 JavaScript 进行访问（也可以通过其他编程语言）。

在 DOM 中，所有 HTML 元素都被定义为对象。

编程界面是每个对象的属性和方法。

属性是您能够获取或设置的值（就比如改变 HTML 元素的内容）。

方法是您能够完成的动作（比如添加或删除 HTML 元素）。

例如：getElementById 是方法，而 innerHTML 是属性。

``` html 
<html>
<body>

<p id="demo"></p>

<script>
document.getElementById("demo").innerHTML = "Hello World!";
</script>

</body>
</html>
```

### getElementById 方法

访问 HTML 元素最常用的方法是使用元素的 id。

### innerHTML 属性

获取元素内容最简单的方法是使用 innerHTML 属性。

innerHTML 属性可用于获取或替换 HTML 元素的内容。

innerHTML 属性可用于获取或改变任何 HTML 元素，包括 `<html>` 和 `<body>`。

## JavaScript HTML DOM 文档

> HTML DOM 文档对象是您的网页中所有其他对象的拥有者。

### HTML DOM Document 对象

文档对象代表您的网页。

如果您希望访问 HTML 页面中的任何元素，那么您总是从访问 document 对象开始。

### 查找 HTML 元素

| 方法 | 描述 |
| --- | --- |
| document.getElementById(_id_) | 通过元素 id 来查找元素 |
| document.getElementsByTagName(_name_) | 通过标签名来查找元素 |
| document.getElementsByClassName(_name_) | 通过类名来查找元素 |

### 改变 HTML 元素

| 方法 | 描述 |
| --- | --- |
| element.innerHTML = _new html content_ | 改变元素的 inner HTML |
| element.attribute = _new value_ | 改变 HTML 元素的属性值 |
| element.setAttribute(_attribute_, _value_) | 改变 HTML 元素的属性值 |
| element.style.property = _new style_ | 改变 HTML 元素的样式 |

### 添加和删除元素

| 方法 | 描述 |
| --- | --- |
| document.createElement(_element_) | 创建 HTML 元素 |
| document.removeChild(_element_) | 删除 HTML 元素 |
| document.appendChild(_element_) | 添加 HTML 元素 |
| document.replaceChild(_element_) | 替换 HTML 元素 |
| document.write(_text_) | 写入 HTML 输出流 |

### 添加事件处理程序

| 方法 | 描述 |
| --- | --- |
| document.getElementById(id).onclick = function(){_code_} | 向 onclick 事件添加事件处理程序 |

### 查找 HTML 对象

首个 HTML DOM Level 1 (1998)，定义了 11 个 HTML 对象、对象集合和属性。它们在 HTML5 中仍然有效。

后来，在 HTML DOM Level 3，加入了更多对象、集合和属性。

| 属性 | 描述 | DOM |
| --- | --- | --- |
| document.anchors | 返回拥有 name 属性的所有 `<a>` 元素。 | 1 |
| document.applets | 返回所有 `<applet>` 元素（HTML5 不建议使用） | 1 |
| document.baseURI | 返回文档的绝对基准 URI | 3 |
| document.body | 返回 `<body>` 元素 | 1 |
| document.cookie | 返回文档的 cookie | 1 |
| document.doctype | 返回文档的 doctype | 3 |
| document.documentElement | 返回 `<html>` 元素 | 3 |
| document.documentMode | 返回浏览器使用的模式 | 3 |
| document.documentURI | 返回文档的 URI | 3 |
| document.domain | 返回文档服务器的域名 | 1 |
| document.domConfig | 废弃。返回 DOM 配置 | 3 |
| document.embeds | 返回所有 `<embed>` 元素 | 3 |
| document.forms | 返回所有 `<form>` 元素 | 1 |
| document.head | 返回 `<head>` 元素 | 3 |
| document.images | 返回所有 `<img>` 元素 | 1 |
| document.implementation | 返回 DOM 实现 | 3 |
| document.inputEncoding | 返回文档的编码（字符集） | 3 |
| document.lastModified | 返回文档更新的日期和时间 | 3 |
| document.links | 返回拥有 href 属性的所有 `<area>` 和 `<a>` 元素 | 1 |
| document.readyState | 返回文档的（加载）状态 | 3 |
| document.referrer | 返回引用的 URI（链接文档） | 1 |
| document.scripts | 返回所有 `<script>` 元素 | 3 |
| document.strictErrorChecking | 返回是否强制执行错误检查 | 3 |
| document.title | 返回 `<title>` 元素 | 1 |
| document.URL | 返回文档的完整 URL | 1 |

## JavaScript HTML DOM 元素

### 查找 HTML 元素

通常，通过 JavaScript，您需要操作 HTML 元素。

为了达成此目的，您需要首先找到这些元素。有好几种完成此任务的方法：

 - 通过 id 查找 HTML 元素
 - 通过标签名查找 HTML 元素
 - 通过类名查找 HTML 元素
 - 通过 CSS 选择器查找 HTML 元素
 - 通过 HTML 对象集合查找 HTML 元素

### 通过 id 查找 HTML 元素

DOM 中查找 HTML 元素最简单的方法是，使用元素的 id。

如果元素被找到，此方法会以对象返回该元素。

如果未找到元素，myElement 将包含 null。

### 通过 CSS 选择器查找 HTML 元素

如果您需要查找匹配指定 CSS 选择器（id、类名、类型、属性、属性值等等）的所有 HTML 元素，请使用 querySelectorAll() 方法。

本例返回 class="intro" 的所有 `<p>` 元素列表：

``` javascript
var x = document.querySelectorAll("p.intro");
```

> querySelectorAll() 不适用于 Internet Explorer 8 及其更早版本。

### 通过 HTML 对象选择器查找 HTML 对象

本例查找 id="frm1" 的 form 元素，在 forms 集合中，然后显示所有元素值：

``` html
<!DOCTYPE html>
<html>
<body>

<h1>使用 document.forms 查找 HTML 元素</h1>

<form id="frm1" action="/demo/action_page.php">
  First name: <input type="text" name="fname" value="Bill"><br>
  Last name: <input type="text" name="lname" value="Gates"><br><br>
  <input type="submit" value="提交">
</form> 

<p>单击“试一试”按钮，显示表单中每个元素的值。</p>

<button onclick="myFunction()">试一试</button>

<p id="demo"></p>

<script>
function myFunction() {
  var x = document.forms["frm1"];
  var text = "";
  var i;
  for (i = 0; i < x.length ;i++) {
    text += x.elements[i].value + "<br>";
  }
  document.getElementById("demo").innerHTML = text;
}
</script>

</body>
</html>
```

## JavaScript HTML DOM - 改变 HTML

### 改变 HTML 输出流

在 JavaScript 中，document.write() 可用于直接写入 HTML 输出流：

``` html
<!DOCTYPE html>
<html>
<body>

<script>
document.write(Date());
</script>

</body>
</html>
```

> 千万不要在文档加载后使用 document.write()。这么做会覆盖文档。

### 改变 HTML 内容

修改 HTML 文档内容最简单的方法是，使用 innerHTML 属性。

如需修改 HTML 元素的内容，请使用此语法：

``` javascript
document.getElementById(id).innerHTML = new text
```

### 改变属性的值

如需修改 HTML 属性的值，请使用如下语法：

``` javascript
document.getElementById(id).attribute = new value
```

本例修改了 <img> 元素的 src 属性的值：

``` javascript
<!DOCTYPE html>
<html>
<body>

<img id="myImage" src="smiley.gif">

<script>
document.getElementById("myImage").src = "landscape.jpg";
</script>

</body>
</html> 
```

例子解释：

 - 上面的 HTML 文档含有一个 id="myImage" 的 `<img>` 元素
 - 我们使用 HTML DOM 来获取 id="myImage" 的元素
 - JavaScript 把此元素的 src 属性从 "smiley.gif" 更改为 "landscape.jpg"

## JavaScript HTML DOM - 改变 CSS

[HTML DOM Style 对象参考手册](https://www.w3school.com.cn/jsref/dom_obj_style.asp)

### 改变 HTML 样式

如需更改 HTML 元素的样式，请使用此语法：

``` javascript
document.getElementById(id).style.property = new style
```

``` javascript
<script>
document.getElementById("p2").style.color = "blue";
</script>
```

### 使用事件

HTML DOM 允许您在事件发生时执行代码。

当“某些事情”在 HTML 元素上发生时，浏览器会生成事件：

 - 点击某个元素时
 - 页面加载时
 - 输入字段被更改时

``` html
<!DOCTYPE html>
<html>
<body>

<h1 id="id1">我的标题 1</h1>

<button type="button" onclick="document.getElementById('id1').style.color = 'red'">
点击我！
</button>

</body>
</html>
```

## JavaScript HTML DOM 事件

[HTML DOM 事件对象参考手册](https://www.w3school.com.cn/jsref/dom_obj_event.asp)

### 对事件作出反应

JavaScript 能够在事件发生时执行，比如当用户点击某个 HTML 元素时。

为了在用户点击元素时执行代码，请向 HTML 事件属性添加 JavaScript 代码：

``` javascript
onclick=JavaScript
```

HTML 事件的例子：

 - 当用户点击鼠标时
 - 当网页加载后
 - 当图像加载后
 - 当鼠标移至元素上时
 - 当输入字段被改变时
 - 当 HTML 表单被提交时
 - 当用户敲击按键时

### HTML 事件属性

如需向 HTML 元素分配事件，您能够使用事件属性。

向 button 元素分配 onclick 事件：

``` html
<button onclick="displayDate()">试一试</button>
```

### 使用 HTML DOM 分配事件

HTML DOM 允许您使用 JavaScript 向 HTML 元素分配事件：

``` html
<script>
document.getElementById("myBtn").onclick = displayDate;

function displayDate() {
  document.getElementById("demo").innerHTML = Date();
}
</script>
```

### onload 和 onunload 事件

当用户进入后及离开页面时，会触发 onload 和 onunload 事件。

onload 事件可用于检测访问者的浏览器类型和浏览器版本，然后基于该信息加载网页的恰当版本。

onload 和 onunload 事件可用于处理 cookie。

``` html
<script>
function checkCookies() {
  var text = "";
  if (navigator.cookieEnabled == true) {
    text = "Cookie 已启用";
  } else {
    text = "Cookie 未启用";
  }
  document.getElementById("demo").innerHTML = text;
}
</script>
```

### onchange 事件

onchange 事件经常与输入字段验证结合使用。

下面是一个如何使用 onchange 的例子。当用户改变输入字段内容时，会调用 upperCase() 函数。

``` html
<!DOCTYPE html>
<html>
<head>
<script>
function myFunction() {
  var x = document.getElementById("fname");
  x.value = x.value.toUpperCase();
}
</script>
</head>
<body>

请输入您的名字：<input type="text" id="fname" onchange="myFunction()">

<p>离开输入字段时，会触发一个函数，将输入文本转换为大写。</p>

</body>
</html>
```
### onmouseover 和 onmouseout 事件

onmouseover 和 onmouseout 事件可用于当用户将鼠标移至 HTML 元素上或移出时触发某个函数：

``` html
<div onmouseover="mOver(this)" onmouseout="mOut(this)" 
style="background-color:#D94A38;width:120px;height:20px;padding:40px;">
请把鼠标移上来</div>

<script>
function mOver(obj) {
  obj.innerHTML = "谢谢您"
}

function mOut(obj) {
  obj.innerHTML = "请把鼠标移上来"
}
</script>
```

### onmousedown, onmouseup 以及 onclick 事件

onmousedown, onmouseup 以及 onclick 事件构成了完整的鼠标点击事件。

首先当鼠标按钮被点击时，onmousedown 事件被触发；然后当鼠标按钮被释放时，onmouseup 事件被触发；最后，当鼠标点击完成后，onclick 事件被触发。

## JavaScript HTML DOM 事件监听器

### addEventListener() 方法

添加当用户点击按钮时触发的事件监听器：

``` javascript
document.getElementById("myBtn").addEventListener("click", displayDate);
```

 - addEventListener() 方法为指定元素指定事件处理程序。
 - addEventListener() 方法为元素附加事件处理程序而不会覆盖已有的事件处理程序。
 - 您能够向一个元素添加多个事件处理程序。
 - 您能够向一个元素添加多个相同类型的事件处理程序，例如两个 "click" 事件。
 - 您能够向任何 DOM 对象添加事件处理程序而非仅仅 HTML 元素，例如 window 对象。
 - addEventListener() 方法使我们更容易控制事件如何对冒泡作出反应。
 - 当使用 addEventListener() 方法时，JavaScript 与 HTML 标记是分隔的，已达到更佳的可读性；即使在不控制 HTML 标记时也允许您添加事件监听器。
 - 您能够通过使用 removeEventListener() 方法轻松地删除事件监听器。

**语法**

``` javascript
element.addEventListener(event, function, useCapture);
```

 - 第一个参数是事件的类型（比如 "click" 或 "mousedown"）。
 - 第二个参数是当事件发生时我们需要调用的函数。
 - 第三个参数是布尔值，指定使用事件冒泡还是事件捕获。此参数是可选的。

> 注意：请勿对事件使用 "on" 前缀；请使用 "click" 代替 "onclick"。

### 向元素添加事件处理程序

当用户点击某个元素时提示 "Hello World!"：

``` javascript
element.addEventListener("click", function(){ alert("Hello World!"); });
```

您也可以引用外部“命名”函数：

当用户点击某个元素时提示 "Hello World!"：

``` javascript
element.addEventListener("click", myFunction);

function myFunction() {
    alert ("Hello World!");
}
```
### 向相同元素添加多个事件处理程序

addEventListener() 方法允许您向相同元素添加多个事件，同时不覆盖已有事件：

``` javascript
element.addEventListener("click", myFunction);
element.addEventListener("click", mySecondFunction);
```

亲自试一试
您能够向相同元素添加不同类型的事件：

``` javascript
element.addEventListener("mouseover", myFunction);
element.addEventListener("click", mySecondFunction);
element.addEventListener("mouseout", myThirdFunction);
```

### 向 Window 对象添加事件处理程序

addEventListener() 允许您将事件监听器添加到任何 HTML DOM 对象上，比如 HTML 元素、HTML 对象、window 对象或其他支持事件的对象，比如 xmlHttpRequest 对象。

添加当用户调整窗口大小时触发的事件监听器：

``` javascript
window.addEventListener("resize", function(){
    document.getElementById("demo").innerHTML = sometext;
});
```

### 传递参数

当传递参数值时，请以参数形式使用调用指定函数的“匿名函数”：

``` html
<script>
var p1 = 5;
var p2 = 7;

document.getElementById("myBtn").addEventListener("click", function() {
  myFunction(p1, p2);
});

function myFunction(a, b) {
  var result = a * b;
  document.getElementById("demo").innerHTML = result;
}
</script>
```

### 事件冒泡还是事件捕获？

在 HTML DOM 中有两种事件传播的方法：冒泡和捕获。

事件传播是一种定义当发生事件时元素次序的方法。假如 `<div>` 元素内有一个 `<p>`，然后用户点击了这个 `<p>` 元素，应该首先处理哪个元素“click”事件？

在冒泡中，最内侧元素的事件会首先被处理，然后是更外侧的：首先处理 `<p>` 元素的点击事件，然后是 `<div>` 元素的点击事件。

在捕获中，最外侧元素的事件会首先被处理，然后是更内侧的：首先处理 `<div>` 元素的点击事件，然后是 `<p>` 元素的点击事件。

在 addEventListener() 方法中，你能够通过使用“useCapture”参数来规定传播类型：

``` javascript
addEventListener(event, function, useCapture);
```

默认值是 false，将使用冒泡传播，如果该值设置为 true，则事件使用捕获传播。

### removeEventListener() 方法

removeEventListener() 方法会删除已通过 addEventListener() 方法附加的事件处理程序：

``` javascript
element.removeEventListener("mousemove", myFunction);
```

### 浏览器支持

注释：IE 8、Opera 6.0 及其更早版本不支持 addEventListener() 和 removeEventListener() 方法。不过，对于这些特殊的浏览器版本，您可以使用 attachEvent() 方法向元素添加事件处理程序，并由 detachEvent() 方法删除：

``` javascript
element.attachEvent(event, function);
element.detachEvent(event, function);
```

跨浏览器解决方案：

``` javascript
var x = document.getElementById("myBtn");
if (x.addEventListener) {                    // 针对主流浏览器，除了 IE 8 及更正版本
    x.addEventListener("click", myFunction);
} else if (x.attachEvent) {                  // 针对 IE 8 及更早版本
    x.attachEvent("onclick", myFunction);
} 
```

## [JavaScript HTML DOM 导航](https://www.w3school.com.cn/js/js_htmldom_navigation.asp)

### 子节点和节点值

DOM 处理中的一种常见错误是认为元素节点中包含文本。

``` javascript
<title id="demo">DOM 教程</title> 
```

（上面例子中的）元素节点 `<title>` 不包含文本。

它包含了值为 "DOM 教程" 的文本节点。

文本节点的值能够通过节点的 innerHTML 属性进行访问：

``` javascript
var myTitle = document.getElementById("demo").innerHTML;
```

访问 innerHTML 属性等同于访问首个子节点的 nodeValue：

``` javascript
var myTitle = document.getElementById("demo").firstChild.nodeValue;
```

也可以这样访问第一个子节点：

``` javascript
var myTitle = document.getElementById("demo").childNodes[0].nodeValue;
```

### DOM 根节点

有两个特殊属性允许访问完整文档：

 - document.body - 文档的 body
 - document.documentElement - 完整文档

### nodeName 属性

nodeName 属性规定节点的名称。

nodeName 是只读的

 - 元素节点的 nodeName 等同于标签名
 - 属性节点的 nodeName 是属性名称
 - 文本节点的 nodeName 总是 #text
 - 文档节点的 nodeName 总是 #document

``` html
<h1 id="id01">我的第一张网页</h1>
<p id="id02">Hello!</p>

<script>
document.getElementById("id02").innerHTML  = document.getElementById("id01").nodeName;	//H1
</script>
```

> 注释：nodeName 总是包含 HTML 元素的大写标签名。

### nodeValue 属性

nodeValue 属性规定节点的值。

 - 元素节点的 nodeValue 是 undefined
 - 文本节点的 nodeValue 是文本文本
 - 属性节点的 nodeValue 是属性值

### nodeType 属性

nodeType 属性返回节点的类型。nodeType 是只读的。

最重要的 nodeType 属性是：

| 节点 | 类型 | 例子 |
| --- | --- | --- |
| ELEMENT_NODE | 1 | `<h1 class="heading">`W3School`</h1>` |
| ATTRIBUTE_NODE | 2 | class = "heading" （弃用） |
| TEXT_NODE | 3 | W3School |
| COMMENT_NODE | 8 | <!-- 这是注释 --> |
| DOCUMENT_NODE | 9 | HTML 文档本身（`<html>` 的父） |
| DOCUMENT_TYPE_NODE | 10 | <!Doctype html> |

Type 2 在 HTML DOM 中已弃用。XML DOM 中未弃用。

## JavaScript HTML DOM 元素（节点）

### 创建新 HTML 元素（节点）

如需向 HTML DOM 添加新元素，您必须首先创建这个元素（元素节点），然后将其追加到已有元素。

``` html
<div id="div1">
<p id="p1">这是一个段落。</p>
<p id="p2">这是另一个段落。</p>
</div>

<script>
//创建了一个新的 <p> 元素
var para = document.createElement("p");
//如需向 <p> 元素添加文本，则必须首先创建文本节点。这段代码创建了一个文本节点
var node = document.createTextNode("这是新文本。");
//向 <p> 元素追加这个文本节点
para.appendChild(node);

//最后您需要向已有元素追加这个新元素。
//这段代码查找一个已有的元素
var element = document.getElementById("div1");
//向这个已有的元素追加新元素
element.appendChild(para);
</script>
```

### 删除已有 HTML 元素

如需删除某个 HTML 元素，您需要知晓该元素的父：

``` html
<!--这个 HTML 文档包含了一个带有两个子节点（两个 <p> 元素）的 <div> 元素-->
<div id="div1">
<p id="p1">这是一个段落。</p>
<p id="p2">这是另一个段落。</p>
</div>

<script>
//查找 id="div1" 的元素
var parent = document.getElementById("div1");
//查找 id="p1" 的 <p> 元素
var child = document.getElementById("p1");
//从父删除子
parent.removeChild(child);
</script>
```

能够在不引用父的情况下删除某个元素是极好的。

但是很遗憾。DOM 需要同时了解您需要删除的元素及其父。

这是一种常见的解决方法：找到你想要删除的子，并利用其 parentNode 属性找到父：

``` javascript
var child = document.getElementById("p1");
child.parentNode.removeChild(child);
```

### 替换 HTML 元素

如需替换元素的，请使用 replaceChild() 方法：

``` html
<div id="div1">
<p id="p1">这是一个段落。</p>
<p id="p2">这是另一个段落。</p>
</div>

<script>
var para = document.createElement("p");
var node = document.createTextNode("这是新文本。");
para.appendChild(node);

var parent = document.getElementById("div1");
var child = document.getElementById("p1");
parent.replaceChild(para, child);
</script>
```

## JavaScript HTML DOM 集合

### HTMLCollection 对象

getElementsByTagName() 方法返回 HTMLCollection 对象。

HTMLCollection 对象是类数组的 HTML 元素列表（集合）。

下面的代码选取文档中的所有 `<p>` 元素：

``` javascript
var x = document.getElementsByTagName("p");
```

该集合中的元素可通过索引号进行访问。

如需访问第二个 `<p>` 元素，您可以这样写：

``` javascript
y = x[1];
```

注释：索引从 0 开始。

### HTML HTMLCollection 长度

length 属性定义了 HTMLCollection 中元素的数量：

``` javascript
var myCollection = document.getElementsByTagName("p");
document.getElementById("demo").innerHTML = myCollection.length;
```

实例解释：
创建所有 `<p>` 元素的集合
显示集合的长度
length 属性在您需要遍历集合中元素时是有用的：

改变所有 `<p>` 元素的背景色：

``` javascript
var myCollection = document.getElementsByTagName("p");
var i;
for (i = 0; i < myCollection.length; i++) {
    myCollection[i].style.backgroundColor = "red";
}
```

### HTMLCollection 并非数组！

HTMLCollection 也许看起来像数组，但并非数组。

您能够遍历列表并通过数字引用元素（就像数组那样）。

不过，您无法对 HTMLCollection 使用数组方法，比如 valueOf()、pop()、push() 或 join()。

## JavaScript HTML DOM 节点列表

### HTML DOM NodeList 对象

NodeList 对象是从文档中提取的节点列表（集合）。

NodeList 对象与 HTMLCollection 对象几乎相同。

如使用 getElementsByClassName() 方法，某些（老的）浏览器会返回 NodeList 对象而不是 HTMLCollection。

所有浏览器都会为 childNodes 属性返回 NodeList 对象。

大多数浏览器会为 querySelectorAll() 方法返回 NodeList 对象。

下面的代码选取文档中的所有 `<p>` 节点：

``` javascript
var myNodeList = document.querySelectorAll("p");
```

NodeList 中的元素可通过索引号进行访问。

如需访问第二个 `<p>` 节点，您可以这样写：

``` javascript
y = myNodeList[1];
```

注释：索引从 0 开始。

### HTML DOM Node List 长度

length 属性定义节点列表中的节点数：

``` javascript
var myNodelist = document.querySelectorAll("p");
document.getElementById("demo").innerHTML = myNodelist.length;
```

### HTMLCollection 与 NodeList 的区别

 - HTMLCollection是 HTML 元素的集合。
 - NodeList 是文档节点的集合。
 - NodeList 和 HTML 集合几乎完全相同。

HTMLCollection 和 NodeList 对象都是类数组的对象列表（集合）。

它们都有定义列表（集合）中项目数的 length 属性。

它们都可以通过索引 (0, 1, 2, 3, 4, ...) 像数组那样访问每个项目。

访问 HTMLCollection 项目，可以通过它们的名称、id 或索引号。

访问 NodeList 项目，只能通过它们的索引号。

只有 NodeList 对象能包含属性节点和文本节点。

节点列表不是数组！

节点数组看起来像数组，但并不是。

您能够遍历节点列表并像数组那样引用其节点。

不过，您无法对节点列表使用数组方法，比如 valueOf()、push()、pop() 或 join()。