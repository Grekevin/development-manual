# JavaScript 手册

## 基础知识

### JavaScript 使用

**`<script>` 标签**

在 HTML 中，JavaScript 代码必须位于 `<script>` 与 `</script>` 标签之间。

> 注释：旧的 JavaScript 例子也许会使用 type 属性：`<script type="text/javascript">`。
> 
> 注释：type 属性不是必需的。JavaScript 是 HTML 中的默认脚本语言。

**`<head>` 或 `<body>` 中的 JavaScript**

能够在 HTML 文档中放置任意数量的脚本。

脚本可被放置与 HTML 页面的 `<body>` 或 `<head>` 部分中，或兼而有之。

> 提示：把脚本置于 `<body>` 元素的底部，可改善显示速度，因为脚本编译会拖慢显示。

**外部脚本**

脚本可放置与外部文件。

外部脚本很实用，如果相同的脚本被用于许多不同的网页。

JavaScript 文件的文件扩展名是 .js。

如需使用外部脚本，请在 `<script>` 标签的 src (source) 属性中设置脚本的名称：

``` javascript
// 外部文件：myScript.js
<script src="myScript.js"></script>
```

可以在 `<head>` 或 `<body>` 中放置外部脚本引用。

该脚本的表现与它被置于 `<script>` 标签中是一样的。

> 注释：外部脚本文件中不能包含 `<script>` 标签。

**外部 JavaScript 的优势**

在外部文件中放置脚本有如下优势：

 - 分离了 HTML 和代码
 - 使 HTML 和 JavaScript 更易于阅读和维护
 - 已缓存的 JavaScript 文件可加速页面加载

如需向一张页面添加多个脚本文件 - 请使用多个 script 标签：

``` javascript
<script src="myScript1.js"></script>
<script src="myScript2.js"></script>
```

**外部引用**

可通过完整的 URL 或相对于当前网页的路径引用外部脚本：

本例使用完整的 URL 来链接至脚本：

``` html
<script src="https://www.w3school.com.cn/js/myScript1.js"></script>
```

本例使用了位于当前网站上指定文件夹中的脚本：

``` html
<script src="/js/myScript1.js"></script>
```

本例链接了与当前页面相同文件夹的脚本：

``` html
<script src="myScript1.js"></script>
```

### JavaScript 输出

> JavaScript 不提供任何内建的打印或显示函数。

**JavaScript 显示方案**

JavaScript 能够以不同方式“显示”数据：

 - 使用 window.alert() 写入警告框
 - 使用 document.write() 写入 HTML 输出
 - 使用 innerHTML 写入 HTML 元素
 - 使用 console.log() 写入浏览器控制台

