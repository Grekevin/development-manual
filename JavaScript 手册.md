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

更改 HTML 元素的 innerHTML 属性是在 HTML 中显示数据的常用方法。

出于测试目的，使用 document.write() 比较方便。

> 注意：在 HTML 文档完全加载后使用 document.write() 将删除所有已有的 HTML 。

提示：document.write() 方法仅用于测试。

### JavaScript 语句

在 HTML 中，JavaScript 语句是由 web 浏览器“执行”的“指令”。

**JavaScript 程序**

计算机程序是由计算机“执行”的一系列“指令”。

在编程语言中，这些编程指令被称为语句。

JavaScript 程序就是一系列的编程语句。

> 注释：在 HTML 中，JavaScript 程序由 web 浏览器执行。

**JavaScript 语句**

JavaScript 语句由以下构成：

值、运算符、表达式、关键词和注释。

大多数 JavaScript 程序都包含许多 JavaScript 语句。

这些语句会按照它们被编写的顺序逐一执行。

> 注释：JavaScript 程序（以及 JavaScript 语句）常被称为 JavaScript 代码。

**分号 ;**

分号分隔 JavaScript 语句。

请在每条可执行的语句之后添加分号：

``` js
a = 5;
b = 6;
c = a + b;
```
如果有分号分隔，允许在同一行写多条语句：

``` js
a = 5; b = 6; c = a + b;
```

> 提示：以分号结束语句不是必需的，但我们仍然强烈建议您这么做。

**JavaScript 空白字符**

JavaScript 会忽略多个空格。您可以向脚本添加空格，以增强可读性。

下面这两行是相等的：

``` js
var person = "Bill";
var person="Bill"; 
```

在运算符旁边（ = + - * / ）添加空格是个好习惯：

``` js
var x = y + z;
```

**JavaScript 行长度和折行**

为了达到最佳的可读性，程序员们常常喜欢把代码行控制在 80 个字符以内。

如果 JavaScript 语句太长，对其进行折行的最佳位置是某个运算符：

``` javascript
document.getElementById("demo").innerHTML =
 "Hello Kitty.";
```

**JavaScript 代码块**

JavaScript 语句可以用花括号（{...}）组合在代码块中。

代码块的作用是定义一同执行的语句。

您会在 JavaScript 中看到成块组合在一起的语句：

``` javascript
function myFunction() {
    document.getElementById("demo").innerHTML = "Hello Kitty.";
    document.getElementById("myDIV").innerHTML = "How are you?";
}
```

**JavaScript 关键词**

JavaScript 语句常常通过某个关键词来标识需要执行的 JavaScript 动作。

![保留字](https://raw.githubusercontent.com/Grekevin/development-manual-imgs/master/1610509470640.png)

> 注释：JavaScript 关键词指的是保留的单词。保留词无法用作变量名。

### JavaScript 语法

JavaScript 语法是一套规则，它定义了 JavaScript 的语言结构。

``` javascript
var x, y;	// 如何声明变量
x = 7; y = 8;	// 如何赋值
z = x + y;	// 如何计算值
```
**JavaScript 值**

JavaScript 语句定义两种类型的值：混合值和变量值。

混合值被称为字面量（literal）。变量值被称为变量。

字符串是文本，由双引号或单引号包围：

``` javascript
"Bill Gates"

'Bill Gates' 
```

**JavaScript 变量**

在编程语言中，变量用于存储数据值。

JavaScript 使用 var 关键词来声明变量。

= 号用于为变量赋值。

在本例中，x 被定义为变量。然后，x 被赋的值是 7：

``` javascript
var x;

x = 7;
```

**JavaScript 表达式**

表达式是值、变量和运算符的组合，计算结果是值。

**JavaScript 注释**

并非所有 JavaScript 语句都被“执行”。

双斜杠 // 或 /* 与 \*/ 之间的代码被视为注释。

注释会被忽略，不会被执行。

**JavaScript 标识符**

标识符是名称。

在 JavaScript 中，标识符用于命名变量（以及关键词、函数和标签）。

在大多数编程语言中，合法名称的规则大多相同。

在 JavaScript 中，首字符必须是字母、下划线（-）或美元符号（$）。

连串的字符可以是字母、数字、下划线或美元符号。

> 提示：数值不可以作为首字符。这样，JavaScript 就能轻松区分标识符和数值。

**JavaScript 对大小写敏感**

所有 JavaScript 标识符对大小写敏感。

变量 lastName 和 lastname，是两个不同的变量。

JavaScript 不会把 VAR 或 Var 译作关键词 var。

**JavaScript 与驼峰式大小写**

历史上，程序员曾使用三种把多个单词连接为一个变量名的方法：

连字符：

<pre>first-name, last-name, master-card, inter-city.</pre>

注释：JavaScript 中不能使用连字符。它是为减法预留的。

下划线：

<pre>first_name, last_name, master_card, inter_city.</pre>

驼峰式大小写（Camel Case）：

<pre>FirstName, LastName, MasterCard, InterCity.</pre>

**JavaScript 程序员倾向于使用以小写字母开头的驼峰大小写：**

<pre>firstName, lastName, masterCard, interCity</pre>

**JavaScript 字符集**

JavaScript 使用 Unicode 字符集。

Unicode 覆盖世界上几乎所有的字符、标点和符号。

### JavaScript 注释

> JavaScript 注释用于解释 JavaScript 代码，增强其可读性。
> 
> JavaScript 注释也可以用于在测试替代代码时阻止执行。

**单行注释**

单行注释以 // 开头。

任何位于 // 与行末之间的文本都会被 JavaScript 忽略（不会执行）。

**多行注释**

多行注释以 /* 开头，以 \*/ 结尾。

任何位于 /* 和 \*/ 之间的文本都会被 JavaScript 忽略。

> 注释：使用单行注释最为常见。
> 
> 提示：注释块常用于官方声明。

**使用注释来阻止执行**

使用注释来防止代码执行很适合代码测试。

在代码行之前添加 // 会把可执行的代码行更改为注释。

### JavaScript 变量

**JavaScript 标识符**

所有 JavaScript 变量必须以唯一的名称的标识。

这些唯一的名称称为标识符。

标识符可以是短名称（比如 x 和 y），或者更具描述性的名称（age、sum、totalVolume）。

构造变量名称（唯一标识符）的通用规则是：

 - 名称可包含字母、数字、下划线和美元符号
 - 名称必须以字母开头
 - 名称也可以 $ 和 _ 开头（但是在本教程中我们不会这么做）
 - 名称对大小写敏感（y 和 Y 是不同的变量）
 - 保留字（比如 JavaScript 的关键词）无法用作变量名称

> 提示：JavaScript 标识符对大小写敏感。

**声明（创建） JavaScript 变量**

在 JavaScript 中创建变量被称为“声明”变量。

您可以通过 var 关键词来声明 JavaScript 变量：

``` javascript
var carName;
```
声明之后，变量是没有值的。（技术上，它的值是 undefined。）

如需赋值给变量，请使用等号：

``` javascript
carName = "porsche";
```
您可以在声明变量时向它赋值：

``` javascript
var carName = "porsche";
```

> 提示：在脚本的开头声明所有变量是个好习惯！

**一条语句，多个变量**

可以在一条语句中声明许多变量。

以 var 作为语句的开头，并以逗号分隔变量：

``` js
var person = "Bill Gates", carName = "porsche", price = 15000;
```

声明可横跨多行：

``` javascript
var person = "Bill Gates",
carName = "porsche",
price = 15000;
```

**Value = undefined**

在计算机程序中，被声明的变量经常是不带值的。值可以是需被计算的内容，或是之后被提供的数据，比如数据输入。

不带有值的变量，它的值将是 undefined。

变量 carName 在这条语句执行后的值是 undefined：

``` javascript
var carName;		//undefined
```

**重复声明 JavaScript 变量**

如果再次声明某个 JavaScript 变量，将不会丢它的值。

在这两条语句执行后，变量 carName 的值仍然是 "porsche"：

``` javascript
var carName = "porsche";
var carName; 
```

**字符串 +**

``` javascript
var x = "8" + 3 + 5;	//835

var x = 3 + 5 + "8";	//88
```

### JavaScript 运算符

[运算符及优先级](https://www.w3school.com.cn/js/js_arithmetic.asp)

