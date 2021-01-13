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

### JavaScript 数据类型

> 字符串值，数值，布尔值，数组，对象。

JavaScript 变量能够保存多种数据类型：数值、字符串值、数组、对象等等：

``` javascript
var length = 7;                             // 数字
var lastName = "Gates";                      // 字符串
var cars = ["Porsche", "Volvo", "BMW"];         // 数组
var x = {firstName:"Bill", lastName:"Gates"};    // 对象 
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

``` JavaScript
for (i = 0; i < 5; i++) {
     text += "数字是 " + i + "<br>";
}
```

从上面的代码中，您可以了解到：

 - 语句 1 在循环开始之前设置了一个变量（var i = 0）。
 - 语句 2 定义运行循环的条件（i 必须小于 5）。
 - 语句 3 会在代码块每次执行之后对值进行递增（i++）。

**语句 1**

通常，使用语句 1 来初始化循环中所使用的的变量（i = 0）。

但情况并不总是这样，JavaScript 不会在意。语句 1 是可选的。

您可以在语句 1 中初始化多个值（由逗号分隔）：

``` javascript
for (i = 0, len = cars.length, text = ""; i < len; i++) { 
    text += cars[i] + "<br>";
}
```

而且您还可以省略语句 1（比如在循环开始前设置好值）：

``` javascript
var i = 2;
var len = cars.length;
var text = "";
for (; i < len; i++) { 
    text += cars[i] + "<br>";
}
```

**语句 2**

通常语句 2 用于计算初始变量的条件。

但情况并不总是这样，JavaScript 不会在意。语句 2 也是可选的。

如果语句 2 返回 true，那么循环会重新开始，如果返回 false，则循环将结束。

如果省略语句 2，那么必须在循环中提供一个 break。否则循环永远不会结束。

**语句 3**

通常语句 3 会递增初始变量的值。

但情况并不总是这样，JavaScript 不会在意。语句 3 也是可选的。

语句 3 可做任何事情，比如负递增（i--），正递增（i = i + 15），或者任何其他事情。

语句 3 也可被省略（比如当您在循环内递增值时）：

``` javascript
var i = 0;
var len = cars.length;
for (; i < len; ) { 
    text += cars[i] + "<br>";
      i++;
}
```

**For/In 循环**

JavaScript for/in 语句遍历对象的属性：

``` javascript
var person = {fname:"Bill", lname:"Gates", age:62}; 

var text = "";
var x;
for (x in person) {
    text += person[x];
}
```

### JavaScript While 循环

只要条件为 true，循环能够一直执行代码块。

while 循环会一直循环代码块，只要指定的条件为 true。

语法

``` javascript
while (条件) {
    要执行的代码块
}
```

**Do/While 循环**

do/while 循环是 while 循环的变体。在检查条件是否为真之前，这种循环会执行一次代码块，然后只要条件为真就会重复循环。

语法

``` JavaScript
do {
    要执行的代码块
}

while (条件);
```

### JavaScript Break 和 Continue

> break 语句“跳出”循环。
> continue 语句“跳过”循环中的一个迭代。

**Break 语句**

break 语句也可用于跳出循环。

break 语句会中断循环，并继续执行循环之后的代码（如果有）。

**Continue 语句**

continue 语句中断（循环中）的一个迭代，如果发生指定的条件。然后继续循环中的下一个迭代。

**JavaScript 标签**

如需标记 JavaScript 语句，请将标签名和冒号置于语句之前：

``` javascript
label:
statements
```
break 和 continue 语句是仅有的可“跳出”代码块的 JavaScript 语句。

语法：

``` javascript
break labelname;
continue labelname;
```

continue 语句（不论有无标签引用）只能用于跳过一个迭代。

break 语句，如果没有标签引用，只能用于跳出一个循环或一个 switch。

如果有标签引用，则 break 语句可用于跳出任意代码块：

``` javascript
var cars = ["BMW", "Volvo", "porsche", "Ford"];
var text = "";

list: {
  text += cars[0] + "<br>"; 
  text += cars[1] + "<br>"; 
  break list;
  text += cars[2] + "<br>"; 
  text += cars[3] + "<br>"; 
}

document.getElementById("demo").innerHTML = text;  //BMW  Volvo
```

> 代码块指的是 { 与 } 直接的代码片段。

### JavaScript 类型转换

> Number() 转换数值，String() 转换字符串，Boolean() 转换布尔值。

**JavaScript 数据类型**

JavaScript 中有五种可包含值的数据类型：

 - 字符串（string）
 - 数字（number）
 - 布尔（boolean）
 - 对象（object）
 - 函数（function）

有三种对象类型：

 - 对象（Object）
 - 日期（Date）
 - 数组（Array）

同时有两种不能包含值的数据类型：

 - null
 - undefined

**typeof 运算符**

使用 typeof 运算符来确定 JavaScript 变量的数据类型。

示例：

``` javascript
typeof "Bill"                 // 返回 "string"
typeof 3.14                   // 返回 "number"
typeof NaN                    // 返回 "number"
typeof false                  // 返回 "boolean"
typeof [1,2,3,4]              // 返回 "object"
typeof {name:'Bill', age:62}  // 返回 "object"
typeof new Date()             // 返回 "object"
typeof function () {}         // 返回 "function"
typeof myCar                  // 返回 "undefined" *
typeof null                   // 返回 "object"
```

请注意：

 - NaN 的数据类型是数值
 - 数组的数据类型是对象
 - 日期的数据类型是对象
 - null 的数据类型是对象
 - 未定义变量的数据类型是 undefined
 - 尚未赋值的变量的数据类型也是 undefined

> 您无法使用 typeof 去判断 JavaScript 对象是否是数组（或日期）。

**typeof 的数据类型**

typeof 运算符不是变量。它属于运算符。运算符（比如 + - * /）没有数据类型。

> typeof 始终会返回字符串（包含运算数的类型）。

**constructor 属性**

constructor 属性返回所有 JavaScript 变量的构造器函数。

``` javascript
"Bill".constructor                 // 返回 "function String()  { [native code] }"
(3.14).constructor                 // 返回 "function Number()  { [native code] }"
false.constructor                  // 返回 "function Boolean() { [native code] }"
[1,2,3,4].constructor              // 返回 "function Array()   { [native code] }"
{name:'Bill', age:62}.constructor  // 返回" function Object()  { [native code] }"
new Date().constructor             // 返回 "function Date()    { [native code] }"
function () {}.constructor         // 返回 "function Function(){ [native code] }"
```
可以通过检查 constructor 属性来确定某个对象是否为数组（包含单词 "Array"）：

``` JavaScript
function isArray(myArray) {
    return myArray.constructor.toString().indexOf("Array") > -1;
}
```

或者更简单，您可以检查对象是否是数组函数：

``` javascript
function isArray(myArray) {
    return myArray.constructor === Array;
}
```

**JavaScript 类型转换**

JavaScript 变量能够被转换为新变量以及另一种数据类型：

 - 通过使用 JavaScript 函数
 - 通过 JavaScript 本身自动转换

**数值转换为字符串**

全局方法 String() 能够把数字转换为字符串。

它可用于任意类型的数字、文字、变量或表达式：

``` javascript
<script>
var x = 123;
document.getElementById("demo").innerHTML =
  String(x) + "<br>" +   //123
  String(123) + "<br>" +  //123
  String(100 + 23);   //123
</script>
```
数字方法 toString() 同理。

``` javascript
x.toString()
(123).toString()
(100 + 23).toString()
```

将数值转换为字符串的方法：

![数值转字符串](https://raw.githubusercontent.com/Grekevin/development-manual-imgs/master/1610520658587.png)

**布尔转换为字符串**

全局方法 String() 能够将布尔转换为字符串。

``` JavaScript
String(false)        // 返回 "false"
String(true)         // 返回 "true" 
```
布尔方法 toString() 同理。

``` javascript
false.toString()     // 返回 "false"
true.toString()      // 返回 "true"
```

**日期转换为字符串**

全局方法 String() 可将日期转换为字符串。

``` javascript
String(Date())      // 返回 "Wed Jan 13 2021 14:49:58 GMT+0800 (China Standard Time)"
```

日期方法 toString() 同理。

``` javascript
Date().toString()   // 返回 "Wed Jan 13 2021 14:49:58 GMT+0800 (China Standard Time)"
```

把日期转换为字符串的方法：

![日期转字符串](https://raw.githubusercontent.com/Grekevin/development-manual-imgs/master/1610520888405.png)

**字符串转换为数值**

全局方法 Number() 可把字符串转换为数字。

包含数字的字符串（比如 "3.14"）转换为数字（比如 3.14）。

空的字符串转换为 0。

其他字符串将转换为 NaN（Not a number，不是数字）。

``` javascript
Number("3.14")    // 返回 3.14
Number(" ")       // 返回 0
Number("")        // 返回 0
Number("99 88")   // 返回 NaN
```

字符串转换为数字的方法：

![字符串转数字](https://raw.githubusercontent.com/Grekevin/development-manual-imgs/master/1610521195054.png)

**一元 + 运算符**

一元的 + 运算符可用于把变量转换为数字：

``` javascript
var y = "5";      // y 是字符串
var x = + y;      // x 是数字
```

如果无法转换变量，则仍会成为数字，但是值为 NaN（Not a number）：

``` javascript
var y = "Bill";   // y 是字符串
var x = + y;      // x 是数字 (NaN)
```

**布尔转换数值**
全局方法 Number() 也可把布尔转换为数字。

``` javascript
Number(false)     // 返回 0
Number(true)      // 返回 1
```

**日期转换为数字**

全局方法 Number() 可用于把日期转换为数字。

``` javascript
d = new Date();
Number(d)          // 返回 1610520598192
```

日期方法 getTime() 同理。

``` javascript
d = new Date();
d.getTime()        // 返回 1610520598192
```

**自动类型转换**

如果 JavaScript 尝试操作一种“错误”的数据类型，它会试图将该值转换为“正确”的类型。

结果并不总是你所期望的：

``` javascript
5 + null    // 返回 5         因为 null 被转换为 0
"5" + null  // 返回 "5null"   因为 null 被转换为  "null"
"5" + 2     // 返回 52        因为 2 被转换为 "2"
"5" - 2     // 返回 3         因为 "5" 被转换为 5
"5" * "2"   // 返回 10        因为 "5" 和 "2" 被转换为 5 和 2
```

**自动字符串转换**

JavaScript 自动调用变量的 toString() 函数，当您试图“输出”对象或变量时：

``` javascript
document.getElementById("demo").innerHTML = myVar;

// 如果 myVar = {name:"Fjohn"}  // toString 转换为 "[object Object]"
// 如果 myVar = [1,2,3,4]       // toString 转换为 "1,2,3,4"
// 如果 myVar = new Date()      // toString 转换为 "Wed Jan 13 2021 14:49:58 GMT+0800 (China Standard Time)"
```

数字和布尔也会被转换，但并不明显：

``` javascript
// 如果 myVar = 123             // toString 转换为 "123"
// 如果 myVar = true            // toString 转换为 "true"
// 如果 myVar = false           // toString 转换为 "false"
```

**JavaScript 类型转换表**

下表中列出了将不同 JavaScript 值转换为数字、字符串和布尔的结果：

[官方参考](https://www.w3school.com.cn/js/js_type_conversion.asp)

### JavaScript 位运算符

**JavaScript 使用 32 位按位运算数**

JavaScript 将数字存储为 64 位浮点数，但所有按位运算都以 32 位二进制数执行。

在执行位运算之前，JavaScript 将数字转换为 32 位有符号整数。

执行按位操作后，结果将转换回 64 位 JavaScript 数。

由于 JavaScript 使用 32 位有符号整数，JavaScript 将返回 -6。

00000000000000000000000000000101 (5)

11111111111111111111111111111010 (~5 = -6)

有符号整数使用最左边的位作为减号。

[官方参考](https://www.w3school.com.cn/js/js_bitwise.asp)

**十进制转换为二进制**

``` javascript
<script>
document.getElementById("demo").innerHTML = dec2bin(-5);
function dec2bin(dec){
  return (dec >>> 0).toString(2);
}
</script>
```

**二进制转换为十进制**

``` javascript
<script>
document.getElementById("demo").innerHTML = bin2dec(101);
function bin2dec(bin){
  return parseInt(bin, 2).toString(10);
}
</script>
```

