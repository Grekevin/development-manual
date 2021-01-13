* [JavaScript 手册](#javascript-手册)
	* [基础知识](#基础知识)
		* [JavaScript 使用](#javascript-使用)
		* [JavaScript 输出](#javascript-输出)
		* [JavaScript 语句](#javascript-语句)
		* [JavaScript 语法](#javascript-语法)
		* [JavaScript 注释](#javascript-注释)
		* [JavaScript 变量](#javascript-变量)
		* [JavaScript 运算符](#javascript-运算符)
		* [JavaScript If...Else 语句](#javascript-ifelse-语句)
		* [JavaScript Switch 语句](#javascript-switch-语句)
		* [JavaScript For 循环](#javascript-for-循环)

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

**JavaScript 比较运算符**

![比较运算符](https://raw.githubusercontent.com/Grekevin/development-manual-imgs/master/1610517077926.png)

**条件（三元）运算符**

JavaScript 也包含了可基于某些条件向变量赋值的条件运算符。

语法

``` js
variablename = (condition) ? value1:value2
```

实例

``` js
var voteable = (age < 18) ? "太年轻":"足够成熟";
```

**比较不同的类型**

比较不同类型的数据也许会出现不可预料的结果。

如果将字符串与数字进行比较，那么在做比较时 JavaScript 会把字符串转换为数值。空字符串将被转换为 0。非数值字符串将被转换为始终为 `false` 的 `NaN`。

![案例](https://raw.githubusercontent.com/Grekevin/development-manual-imgs/master/1610517389177.png)

当比较两个字符串时，"2" 大于 "12"，因为（按照字母排序）1 小于 2。

为了确保正确的结果，在比较值前应该把变量转换为合适的类型：

``` javascript
age = Number(age);
if (isNaN(age)) {
    voteable = "输入错误";
} else {
    voteable = (age < 18) ? "太年轻" : "足够成熟";
} 
```

### JavaScript If...Else 语句

条件语句用于基于不同条件执行不同的动作。

在 JavaScript 中，我们可使用如下条件语句：

 - 使用 if 来规定要执行的代码块，如果指定条件为 true
 - 使用 else 来规定要执行的代码块，如果相同的条件为 false
 - 使用 else if 来规定要测试的新条件，如果第一个条件为 false
 - 使用 switch 来规定多个被执行的备选代码块

**if 语句**

请使用 if 语句来规定假如条件为 true 时被执行的 JavaScript 代码块。

语法

``` javascript
if (条件) {
    如果条件为 true 时执行的代码
} 
```

注释：if 使用小写字母。大学字母（IF 或 If）会产生 JavaScript 错误。

**else 语句**

请使用 else 语句来规定假如条件为 false 时的代码块。

``` javascript
if (条件) {
    条件为 true 时执行的代码块
} else { 
    条件为 false 时执行的代码块
}
```

**else if 语句**

请使用 else if 来规定当首个条件为 false 时的新条件。

语法

``` javascript
if (条件 1) {
    条件 1 为 true 时执行的代码块
} else if (条件 2) {
    条件 1 为 false 而条件 2 为 true 时执行的代码块
 } else {
    条件 1 和条件 2 同时为 false 时执行的代码块
}
```

### JavaScript Switch 语句

switch 语句用于基于不同条件执行不同动作。

请使用 switch 语句来选择多个需被执行的代码块之一。

语法

``` javascript
switch(表达式) {
     case n:
        代码块
        break;
     case n:
        代码块
        break;
     default:
        默认代码块
} 
```

代码解释：

 - 计算一次 switch 表达式
 - 把表达式的值与每个 case 的值进行对比
 - 如果存在匹配，则执行关联代码

 **break 关键词**

如果 JavaScript 遇到 break 关键词，它会跳出 switch 代码块。

此举将停止代码块中更多代码的执行以及 case 测试。

如果找到匹配，并完成任务，则随机中断执行（break）。无需更多测试。

break 能够节省大量执行时间，因为它会“忽略” switch 代码块中的其他代码的执行。

不必中断 switch 代码块中的最后一个 case。代码块在此处会自然结束。

**default 关键词**

default 关键词规定不存在 case 匹配时所运行的代码。

默认的 case 不必是 switch 代码块中最后一个 case：

``` JavaScript
switch (new Date().getDay()) {
    default: 
        text = "期待周末！";
         break;
    case 6:
        text = "今天是周六";
        break; 
    case 0:
        text = "今天是周日";
} 
```

如果 default 不是 switch 代码块中最后一个 case，请记得用 break 结束默认 case。

**常见的代码块**

有时您会需要不同的 case 来使用相同的代码。

在本例中，case 4 和 5 分享相同的代码块，而 0 和 6 分享另一段代码块：

``` javascript
switch (new Date().getDay()) {
    case 4:
    case 5:
        text = "周末快到了：）";
        break; 
    case 0:
    case 6:
        text = "今天是周末~";
         break;
    default: 
        text = "期待周末！";
} 
```

**Switching 的细节**

如果多种 case 匹配一个 case 值，则选择第一个 case。

如果未找到匹配的 case，程序将继续使用默认 label。

如果未找到默认 label，程序将继续 switch 后的语句。

**严格的比较**

Switch case 使用严格比较（===）。

值必须与要匹配的类型相同。

只有操作数属于同一类型时，严格比较才能为 true。

在这个例子中，x 将不匹配：

``` javascript
var x = "0";
switch (x) {
  case 0:
    text = "Off";
    break;
  case 1:
    text = "On";
    break;
  default:
    text = "No value found";
}
```

### JavaScript For 循环

循环可多次执行代码块。

**不同类型的循环**

JavaScript 支持不同类型的循环：

 - for - 多次遍历代码块
 - for/in - 遍历对象属性
 - while - 当指定条件为 true 时循环一段代码块
 - do/while - 当指定条件为 true 时循环一段代码块

**For 循环**

for 循环是创建循环时经常使用的工具。

for 循环的语法如下：

``` javascript
for (语句 1; 语句 2; 语句 3) {
     要执行的代码块
}
```

 - 语句 1 在循环（代码块）开始之前执行。
 - 语句 2 定义运行循环（代码块）的条件。
 - 语句 3 会在循环（代码块）每次被执行后执行。


