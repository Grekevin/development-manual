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

