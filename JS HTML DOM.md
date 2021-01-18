
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

