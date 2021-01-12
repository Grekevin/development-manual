## HTML DOM 教程

### HTML DOM 树

![HTML DOM 树](https://raw.githubusercontent.com/Grekevin/development-manual-imgs/master/1610461034647.png)

通过 HTML DOM，树中的所有节点均可通过 JavaScript 进行访问。所有 HTML 元素（节点）均可被修改，也可以创建或删除节点。

### 什么是 DOM？

DOM 是 W3C（万维网联盟）的标准。

DOM 定义了访问 HTML 和 XML 文档的标准：

“W3C 文档对象模型 （DOM） 是中立于平台和语言的接口，它允许程序和脚本动态地访问和更新文档的内容、结构和样式。”

W3C DOM 标准被分为 3 个不同的部分：

 - 核心 DOM - 针对任何结构化文档的标准模型
 - XML DOM - 针对 XML 文档的标准模型
 - HTML DOM - 针对 HTML 文档的标准模型

> 编者注：DOM 是 Document Object Model（文档对象模型）的缩写。

**HTML DOM 是：**

 - HTML 的标准对象模型
 - HTML 的标准编程接口
 - W3C 标准

HTML DOM 定义了所有 HTML 元素的对象和属性，以及访问它们的方法。

换言之，HTML DOM 是关于如何获取、修改、添加或删除 HTML 元素的标准。

### DOM 节点

根据 W3C 的 HTML DOM 标准，HTML 文档中的所有内容都是节点：

 - 整个文档是一个文档节点
 - 每个 HTML 元素是元素节点
 - HTML 元素内的文本是文本节点
 - 每个 HTML 属性是属性节点
 - 注释是注释节点

**节点父、子和同胞**

节点树中的节点彼此拥有层级关系。

父（parent）、子（child）和同胞（sibling）等术语用于描述这些关系。父节点拥有子节点。同级的子节点被称为同胞（兄弟或姐妹）。

 - 在节点树中，顶端节点被称为根（root）
 - 每个节点都有父节点、除了根（它没有父节点）
 - 一个节点可拥有任意数量的子
 - 同胞是拥有相同父节点的节点

下面的图片展示了节点树的一部分，以及节点之间的关系：

![节点关系](https://raw.githubusercontent.com/Grekevin/development-manual-imgs/master/1610461581182.png)

### HTML DOM 方法

方法是我们可以在节点（HTML 元素）上执行的动作。

**编程接口**

可通过 JavaScript （以及其他编程语言）对 HTML DOM 进行访问。

所有 HTML 元素被定义为对象，而编程接口则是对象方法和对象属性。

方法是您能够执行的动作（比如添加或修改元素）。

属性是您能够获取或设置的值（比如节点的名称或内容）。

**HTML DOM 对象 - 方法和属性**

一些常用的 HTML DOM 方法：

 - getElementById(id) - 获取带有指定 id 的节点（元素）
 - appendChild(node) - 插入新的子节点（元素）
 - removeChild(node) - 删除子节点（元素）

一些常用的 HTML DOM 属性：

 - innerHTML - 节点（元素）的文本值
 - parentNode - 节点（元素）的父节点
 - childNodes - 节点（元素）的子节点
 - attributes - 节点（元素）的属性节点

**一些 DOM 对象方法**

![DOM 常用方法](https://raw.githubusercontent.com/Grekevin/development-manual-imgs/master/1610461988351.png)

### HTML DOM 属性

属性是节点（HTML 元素）的值，您能够获取或设置。

**nodeName 属性**

nodeName 属性规定节点的名称。

 - nodeName 是只读的
 - 元素节点的 nodeName 与标签名相同
 - 属性节点的 nodeName 与属性名相同
 - 文本节点的 nodeName 始终是 #text
 - 文档节点的 nodeName 始终是 #document
 - 注释：nodeName 始终包含 HTML 元素的大写字母标签名。

**nodeValue 属性**

nodeValue 属性规定节点的值。

 - 元素节点的 nodeValue 是 undefined 或 null
 - 文本节点的 nodeValue 是文本本身
 - 属性节点的 nodeValue 是属性值

**nodeType 属性**

nodeType 属性返回节点的类型。nodeType 是只读的。

比较重要的节点类型有：

![节点类型](https://raw.githubusercontent.com/Grekevin/development-manual-imgs/master/1610462328422.png)

下面的例子返回包含文档中所有 `<p>` 元素的列表：

``` javascript
document.getElementsByTagName("p");
```

下面的例子返回包含文档中所有 `<p>` 元素的列表，并且这些 `<p>` 元素应该是 id="main" 的元素的后代（子、孙等等）：

``` js
document.getElementById("main").getElementsByTagName("p");
```

下面的例子返回包含 class="intro" 的所有元素的一个列表：

``` javascript
document.getElementsByClassName("intro");
```

> 注释：getElementsByClassName() 在 Internet Explorer 5,6,7,8 中无效。

### HTML DOM - 修改

修改 HTML = 改变元素、属性、样式和事件。

**修改 HTML 元素**

修改 HTML DOM 意味着许多不同的方面：

 - 改变 HTML 内容
 - 改变 CSS 样式
 - 改变 HTML 属性
 - 创建新的 HTML 元素
 - 删除已有的 HTML 元素
 - 改变事件（处理程序）

**使用事件**

HTML DOM 允许您在事件发生时执行代码。

当 HTML 元素”有事情发生“时，浏览器就会生成事件：

 - 在元素上点击
 - 加载页面
 - 改变输入字段

### HTML DOM - 事件





### 总结

 appendChild() 方法，将新元素作为父元素的最后一个子元素进行添加。
 
 能否在不引用父元素的情况下删除某个元素？

很抱歉。DOM 需要了解您需要删除的元素，以及它的父元素。

这里提供一个常用的解决方法：找到您需要删除的子元素，然后使用 parentNode 属性来查找其父元素：

``` javascript
var child=document.getElementById("p1");
child.parentNode.removeChild(child);
```

