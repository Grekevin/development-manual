
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

### getElementById 方法

访问 HTML 元素最常用的方法是使用元素的 id。

### innerHTML 属性

获取元素内容最简单的方法是使用 innerHTML 属性。

innerHTML 属性可用于获取或替换 HTML 元素的内容。

innerHTML 属性可用于获取或改变任何 HTML 元素，包括 <html> 和 <body>。