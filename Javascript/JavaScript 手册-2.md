* [JavaScript 手册-2](#javascript-手册-2)
		* [JavaScript 函数](#javascript-函数)
		* [JavaScript 对象](#javascript-对象)
		* [JavaScript 事件](#javascript-事件)
		* [JavaScript 字符串](#javascript-字符串)
		* [JavaScript 字符串方法](#javascript-字符串方法)
		* [JavaScript 数字](#javascript-数字)
		* [JavaScript 数值方法](#javascript-数值方法)
		* [JavaScript 数组](#javascript-数组)
		* [JavaScript 数组方法](#javascript-数组方法)
		* [JavaScript 数组排序](#javascript-数组排序)

# JavaScript 手册-2 

### JavaScript 函数

JavaScript 函数是被设计为执行特定任务的代码块。

JavaScript 函数会在某代码调用它时被执行。

**JavaScript 函数语法**

JavaScript 函数通过 function 关键词进行定义，其后是函数名和括号 ()。

函数名可包含字母、数字、下划线和美元符号（规则与变量名相同）。

圆括号可包括由逗号分隔的参数：

``` js
(参数 1, 参数 2, ...)
```

由函数执行的代码被放置在花括号中：{}

``` javascript
function name(参数 1, 参数 2, 参数 3) {
   // 要执行的代码
}
```

函数参数（Function parameters）是在函数定义中所列的名称。

函数参数（Function arguments）是当调用函数时由函数接收的真实的值。

在函数中，参数是局部变量。

在其他编程语言中，函数近似程序（Procedure）或子程序（Subroutine）。

**函数调用**

函数中的代码将在其他代码调用该函数时执行：

 - 当事件发生时（当用户点击按钮时）
 - 当 JavaScript 代码调用时
 - 自动的（自调用）

**函数返回**

当 JavaScript 到达 return 语句，函数将停止执行。

如果函数被某条语句调用，JavaScript 将在调用语句之后“返回”执行代码。

函数通常会计算出返回值。这个返回值会返回给调用者：

实例

计算两个数的乘积，并返回结果：

``` javascript
var x = myFunction(7, 8);        // 调用函数，返回值被赋值给 x

function myFunction(a, b) {
    return a * b;                // 函数返回 a 和 b 的乘积
}
```

x 的结果将是：

``` javascript
56
```

**为何使用函数？**

您能够对代码进行复用：只要定义一次代码，就可以多次使用它。

您能够多次向同一函数传递不同的参数，以产生不同的结果。

实例

把华氏度转换为摄氏度：

``` javascript
function toCelsius(fahrenheit) {
    return (5/9) * (fahrenheit-32);
}

document.getElementById("demo").innerHTML = toCelsius(77);
```

**() 运算符调用函数**

使用上面的例子，toCelsius 引用的是函数对象，而 toCelsius() 引用的是函数结果。

**用作变量值的函数**

函数的使用方法与变量一致，在所有类型的公式、赋值和计算中。

实例

使用变量来存储函数的值：

``` javascript
var x = toCelsius(77);
var text = "The temperature is " + x + " Celsius";
```

您能够把函数当做变量值直接使用：

``` javascript
var text = "The temperature is " + toCelsius(77) + " Celsius";
```
**局部变量**

在 JavaScript 函数中声明的变量，会成为函数的局部变量。

局部变量只能在函数内访问。

由于局部变量只能被其函数识别，因此可以在不同函数中使用相同名称的变量。

局部变量在函数开始时创建，在函数完成时被删除。

### JavaScript 对象

[官方参考](https://www.w3school.com.cn/js/js_objects.asp)

**对象定义**

我们定义（创建）了一个 JavaScript 对象：

实例

``` JavaScript
var person = {firstName:"Bill", lastName:"Gates", age:62, eyeColor:"blue"};
```
空格和折行都是允许的。对象定义可横跨多行：

``` javascript
var person = {
    firstName:"Bill",
    lastName:"Gates",
    age:50,
    eyeColor:"blue"
};
```
**访问对象属性**

您能够以两种方式访问属性：

``` javascript
objectName.propertyName
```

或者

``` javascript
objectName["propertyName"]
```
**访问对象方法**

您能够通过如下语法访问对象方法：

``` javascript
objectName.methodName()
```
如果您不使用 () 访问 fullName 方法，则将返回函数定义：

``` javascript
name = person.fullName;
```
**请不要把字符串、数值和布尔值声明为对象！**

如果通过关键词 "new" 来声明 JavaScript 变量，则该变量会被创建为对象：

``` javascript
var x = new String();        // 把 x 声明为 String 对象
var y = new Number();        // 把 y 声明为 Number 对象
var z = new Boolean();       //	把 z 声明为 Boolean 对象
```

> 请避免字符串、数值或逻辑对象。他们会增加代码的复杂性并降低执行速度。

### JavaScript 事件

HTML 事件是发生在 HTML 元素上的“事情”。

当在 HTML 页面中使用 JavaScript 时，JavaScript 能够“应对”这些事件。

**HTML 事件**

[事件列表](https://www.w3school.com.cn/jsref/dom_obj_event.asp)

HTML 事件可以是浏览器或用户做的某些事情。

下面是 HTML 事件的一些例子：

 - HTML 网页完成加载
 - HTML 输入字段被修改
 - HTML 按钮被点击

通常，当事件发生时，用户会希望做某件事。

JavaScript 允许您在事件被侦测到时执行代码。

通过 JavaScript 代码，HTML 允许您向 HTML 元素添加事件处理程序。

使用单引号：

``` javascript
<element event='一些 JavaScript'>
```

使用双引号：

``` javascript
<element event="一些 JavaScript">
```

在下面的例子中，onclick 属性（以及代码）被添加到 `<button>` 元素：

``` javascript
<button onclick='document.getElementById("demo").innerHTML=Date()'>现在的时间是？</button>
```

在接下来的例子中，代码（使用 this.innerHTML）改变了其自身元素的内容：

``` javascript
<button onclick="this.innerHTML=Date()">现在的时间是？</button>
```

JavaScript 代码通常有很多行。事件属性调用函数更为常见：

``` javascript
<button onclick="displayDate()">现在的时间是？</button>
```

**JavaScript 能够做什么？**

事件处理程序可用于处理、验证用户输入、用户动作和浏览器动作：

 - 每当页面加载时应该做的事情
 - 当页面被关闭时应该做的事情
 - 当用户点击按钮时应该被执行的动作
 - 当用户输入数据时应该被验证的内容
 - 等等

让 JavaScript 处理事件的不同方法有很多：

 - HTML 事件属性可执行 JavaScript 代码
 - HTML 事件属性能够调用 JavaScript 函数
 - 您能够向 HTML 元素分配自己的事件处理函数
 - 您能够阻止事件被发送或被处理
 - 等等

### JavaScript 字符串

JavaScript 字符串用于存储和操作文本。

JavaScript 字符串是引号中的零个或多个字符。

**字符串长度**

内建属性 `length` 可返回字符串的长度：

``` javascript
var txt = "ABCDEFGHIJKLMNOPQRSTUVWXYZ";
var sln = txt.length;
```

**特殊字符**

由于字符串必须由引号包围，JavaScript 会误解这段字符串：

``` javascript
var y = "中国是瓷器的故乡，因此 china 与"China（中国）"同名。"
```

该字符串将被切为 "中国是瓷器的故乡，因此 china 与"。

避免此问题的解决方法是，使用 \ 转义字符。

反斜杠转义字符把特殊字符转换为字符串字符：

![转义字符](https://raw.githubusercontent.com/Grekevin/development-manual-imgs/master/1610531094564.png)

转义字符（\）也可用于在字符串中插入其他特殊字符。

其他六个 JavaScript 中有效的转义序列：

![转义序列](https://raw.githubusercontent.com/Grekevin/development-manual-imgs/master/1610531163799.png)

这六个转义字符最初设计用于控制打字机、电传打字机和传真机。它们在 HTML 中没有任何意义。

**长代码行换行**

为了最佳可读性， 程序员们通常会避免每行代码超过 80 个字符串。

如果某条 JavaScript 语句不适合一整行，那么最佳换行位置是某个运算符之后：

``` javascript
document.getElementById("demo").innerHTML =
"Hello Kitty.";
```

您也可以在字符串中换行，通过一个反斜杠即可：

``` javascript
document.getElementById("demo").innerHTML = "Hello \
Kitty!";
```

\ 方法并不是 ECMAScript (JavaScript) 标准。

某些浏览器也不允许 \ 字符之后的空格。

对长字符串换行的最安全做法（但是有点慢）是使用字符串加法：

``` javascript
document.getElementById("demo").innerHTML = "Hello" + 
"Kitty!";
```

您不能通过反斜杠对代码行进行换行：

``` Javascript
document.getElementById("demo").innerHTML = \ 
"Hello Kitty!";
```

**字符串可以是对象**

通常，JavaScript 字符串是原始值，通过字面方式创建：

``` javascript
var firstName = "Bill"
```

但是字符串也可通过关键词 new 定义为对象：

``` javascript
var firstName = new String("Bill")
```

示例：

``` javascript
var x = "Bill";
var y = new String("Bill");

// typeof x 将返回 string
// typeof y 将返回 object
```

请不要把字符串创建为对象。它会拖慢执行速度。

new 关键字使代码复杂化。也可能产生一些意想不到的结果：

当使用 == 相等运算符时，相等字符串是相等的：

``` javascript
var x = "Bill";             
var y = new String("Bill");
// (x == y) 为 true，因为 x 和 y 的值相等
```

当使用 === 运算符时，相等字符串是不相等的，因为 === 运算符需要类型和值同时相等。

``` javascript
var x = "Bill";             
var y = new String("Bill");
// (x === y) 为 false，因为 x 和 y 的类型不同（字符串与对象）
```

甚至更糟。对象无法比较：

``` javascript
var x = new String("Bill");             
var y = new String("Bill");
// (x == y) 为 false，因为 x 和 y 是不同的对象
```

> 请注意 (x==y) 与 (x===y) 的区别。
JavaScript 对象无法进行对比，比较两个 JavaScript 将始终返回 false。

### JavaScript 字符串方法

[字符串方法](https://www.w3school.com.cn/jsref/jsref_obj_string.asp)

字符串方法帮助您处理字符串。

**字符串方法和属性**

原始值，比如“Bill Gates”，无法拥有属性和方法（因为它们不是对象）。

但是通过 JavaScript，方法和属性也可用于原始值，因为在执行方法和属性时 JavaScript 将原始值视为对象。

**查找字符串中的字符串**

indexOf() 方法返回字符串中指定文本首次出现的索引（位置）：

``` javascript
var str = "The full name of China is the People's Republic of China.";
var pos = str.indexOf("China");	//17
```
JavaScript 从零计算位置。

0 是字符串中的第一个位置，1 是第二个，2 是第三个 ...

lastIndexOf() 方法返回指定文本在字符串中最后一次出现的索引：

``` javascript
var str = "The full name of China is the People's Republic of China.";
var pos = str.lastIndexOf("China"); //51
```

> 如果未找到文本， indexOf() 和 lastIndexOf() 均返回 -1。

两种方法都接受作为检索起始位置的第二个参数。

``` javascript
var str = "The full name of China is the People's Republic of China.";
var pos = str.indexOf("China", 18);	//51
```

lastIndexOf() 方法向后进行检索（从尾到头），这意味着：假如第二个参数是 50，则从位置 50 开始检索，直到字符串的起点。

``` javascript
var str = "The full name of China is the People's Republic of China.";
var pos = str.lastIndexOf("China", 50);	//17
```

**检索字符串中的字符串**

search() 方法搜索特定值的字符串，返回字符串中指定文本第一次出现的位置：

``` javascript
var str = "The full name of China is the People's Republic of China.";
var pos = str.search("China"); //17
```

> indexOf() 与 search()区别在于：
>  - search() 方法无法设置第二个开始位置参数。
>  - indexOf() 方法无法设置更强大的搜索值（正则表达式）。

**提取部分字符串**

有三种提取部分字符串的方法：

 - slice(start, end)
 - substring(start, end)
 - substr(start, length)

**slice() 方法**

slice() 提取字符串的某个部分并在新字符串中返回被提取的部分。

该方法设置两个参数：起始索引（开始位置），终止索引（结束位置）。

这个例子裁剪字符串中位置 7 到位置 13 的片段：

``` javascript
var str = "Apple, Banana, Mango";
var res = str.slice(7,13);	//Banana
```
如果某个参数为负，则从字符串的结尾开始计数。

这个例子裁剪字符串中位置 -12 到位置 -6 的片段：

``` javascript
var str = "Apple, Banana, Mango";
var res = str.slice(-13,-7);	//Banana
```

如果省略第二个参数，则该方法将裁剪字符串的剩余部分：

``` javascript
var str = "Apple, Banana, Mango";
var res = str.slice(7);	//Banana, Mango
var res = str.slice(-13); //Banana, Mango
```
提示：负值位置不适用 Internet Explorer 8 及其更早版本。

**substring() 方法**

substring() 类似于 slice()。

不同之处在于 substring() 无法接受负的索引。

``` javascript
var str = "Apple, Banana, Mango";
var res = str.substring(7,13);	//Banana
```
如果省略第二个参数，则该 substring() 将裁剪字符串的剩余部分。

**substr() 方法**

substr() 类似于 slice()。

不同之处在于第二个参数规定被提取部分的长度。

``` javascript
var str = "Apple, Banana, Mango";
var res = str.substr(7,6);	//Banana
```
如果省略第二个参数，则该 substr() 将裁剪字符串的剩余部分。

``` javascript
var str = "Apple, Banana, Mango";
var res = str.substr(7);	//Banana, Mango
```
如果首个参数为负，则从字符串的结尾计算位置。

``` javascript
var str = "Apple, Banana, Mango";
var res = str.substr(-5);	//Mango
```
第二个参数不能为负，因为它定义的是长度。

**替换字符串内容**

replace() 方法用另一个值替换在字符串中指定的值：

``` javascript
str = "Please visit Microsoft!";
var n = str.replace("Microsoft", "W3School");	//n = Please visit W3Schoo!
```
replace() 方法不会改变调用它的字符串。它返回的是新字符串。

默认地，replace() 只替换首个匹配：

``` javascript
str = "Please visit Microsoft and Microsoft!";
var n = str.replace("Microsoft", "W3School");	//n = Please visit W3School and Microsoft!
```
默认地，replace() 对大小写敏感。因此不对匹配 MICROSOFT：

``` javascript
str = "Please visit Microsoft!";
var n = str.replace("MICROSOFT", "W3School");
```
如需执行大小写不敏感的替换，请使用正则表达式 /i（大小写不敏感）：

``` javascript
str = "Please visit Microsoft!";
var n = str.replace(/MICROSOFT/i, "W3School"); 	//n = "Please visit W3School!"
```
请注意正则表达式不带引号。

如需替换所有匹配，请使用正则表达式的 g 标志（用于全局搜索）：

``` javascript
str = "Please visit Microsoft and Microsoft!";
var n = str.replace(/Microsoft/g, "W3School");	//n = "Please visit W3School and W3School!"
```

**转换为大写和小写**

通过 toUpperCase() 把字符串转换为大写：

``` javascript
var text1 = "Hello World!";       // 字符串
var text2 = text1.toUpperCase();  // text2 是被转换为大写的 HELLO WORLD!
```
通过 toLowerCase() 把字符串转换为小写：

``` javascript
var text1 = "Hello World!";       // 字符串
var text2 = text1.toLowerCase();  // text2 是被转换为小写的 hello world!
```

**concat() 方法**

concat() 连接两个或多个字符串。

concat() 方法可用于代替加运算符。下面两行是等效的：

``` javascript
var text = "Hello" + " " + "World!";
var text = "Hello".concat(" ","World!");
```

> 所有字符串方法都会返回新字符串。它们不会修改原始字符串。
> 正式地说：字符串是不可变的：字符串不能更改，只能替换。

**String.trim()**

trim() 方法删除字符串两端的空白符：

``` javascript
var str = "       Hello World!        ";
var new_str = str.trim();	//Hello World!
```
警告：Internet Explorer 8 或更低版本不支持 trim() 方法。

如需支持 IE 8，您可搭配正则表达式使用 replace() 方法代替：

``` javascript
var str = "       Hello World!        ";
alert(str.replace(/^[\s\uFEFF\xA0]+|[\s\uFEFF\xA0]+$/g, ''));
```

您还可以使用上面的 replace 方案把 trim 函数添加到 JavaScript String.prototype：

``` javascript
if (!String.prototype.trim) {
  String.prototype.trim = function () {
    return this.replace(/^[\s\uFEFF\xA0]+|[\s\uFEFF\xA0]+$/g, '');
};
var str = "       Hello World!        ";
var new_str = str.trim();	//Hello World!
```

**提取字符串字符**

这是两个提取字符串字符的安全方法：

 - charAt(position)
 - charCodeAt(position)

**charAt() 方法**

charAt() 方法返回字符串中指定下标（位置）的字符串：

``` javascript
var str = "HELLO WORLD";
str.charAt(0);            // 返回 H
```

**charCodeAt() 方法**

charCodeAt() 方法返回字符串中指定索引的字符 unicode 编码：

``` javascript
var str = "HELLO WORLD";
str.charCodeAt(0);         // 返回 72
```

**属性访问（Property Access）**

ECMAScript 5 (2009) 允许对字符串的属性访问 [ ]：

``` javascript
var str = "HELLO WORLD";
str[0];                   // 返回 H
```

使用属性访问有点不太靠谱：

 - 不适用 Internet Explorer 7 或更早的版本
 - 它让字符串看起来像是数组（其实并不是）
 - 如果找不到字符，[ ] 返回 undefined，而 charAt() 返回空字符串。
 - 它是只读的。str[0] = "A" 不会产生错误（但也不会工作！）

``` javascript
var str = "HELLO WORLD";
str[0] = "A";             // 不产生错误，但不会工作
str[0];                   // 返回 H
```
提示：如果您希望按照数组的方式处理字符串，可以先把它转换为数组。

**把字符串转换为数组**

可以通过 split() 将字符串转换为数组：

``` javascript
var txt = "a,b,c,d,e";   // 字符串
txt.split(",");          // 用逗号分隔
txt.split(" ");          // 用空格分隔
txt.split("|");          // 用竖线分隔
```
如果省略分隔符，被返回的数组将包含 index [0] 中的整个字符串。

``` javascript
var txt = "Hello";       // 字符串
txt.split()               // ["Hello"]
```

如果分隔符是 ""，被返回的数组将是间隔单个字符的数组：

``` javascript
var txt = "Hello";       // 字符串
txt.split("");           // ["H", "e", "l", "l", "o"]
```

### JavaScript 数字

JavaScript 只有一种数值类型。

书写数值时带不带小数点均可。

书写 JavaScript 数值既可以带小数点，也可以不带：

``` javascript
var x = 3.14;    // 带小数点的数值
var y = 3;       // 不带小数点的数值   也可以写成： var y = 3.00;
```

**JavaScript 数值始终是 64 位的浮点数**

与许多其他编程语言不同，JavaScript 不会定义不同类型的数，比如整数、短的、长的、浮点的等等。

JavaScript 数值始终以双精度浮点数来存储，根据国际 IEEE 754 标准。

此格式用 64 位存储数值，其中 0 到 51 存储数字（片段），52 到 62 存储指数，63 位存储符号：

| 值(aka Fraction/Mantissa) | 指数 | 符号 |
| --- | --- | --- |
| 52 bits(0 - 51) | 11 bits (52 - 62) | 1 bit (63) |

**精度**

整数（不使用指数或科学计数法）会被精确到 15 位。

``` javascript
var x = 999999999999999;   // x 将是 999999999999999
var y = 9999999999999999;  // y 将是 10000000000000000
```

小数的最大数是 17 位，但是浮点的算数并不总是 100% 精准：

``` javascript
var x = 0.2 + 0.1;         // x 将是 0.30000000000000004
```

使用乘除法有助于解决上面的问题：

``` javascript
var x = (0.2 * 10 + 0.1 * 10) / 10;       // x 将是 0.3
```
**数字和字符串相加**

警告！！
JavaScript 的加法和级联（concatenation）都使用 + 运算符。

数字用加法。字符串用级联。

如果您对两个数相加，结果将是一个数：

``` javascript
var x = 10;
var y = 20;
var z = x + y;           // z 将是 30（一个数）
```

如果对两个字符串相加，结果将是一个字符串的级联：

``` javascript
var x = "10";
var y = "20";
var z = x + y;           // z 将是 1020（字符串）
```

如果您对一个数和一个字符串相加，结果也是字符串级联：

``` javascript
var x = 10;
var y = "20";
var z = x + y;           // z 将是 1020（一个字符串）
```
如果您对一个字符串和一个数字相加，结果也是字符串级联：

``` javascript
var x = "10";
var y = 20;
var z = x + y;           // z 将是 1020（字符串）
```
常见的错误是认为结果应该是 30：

``` javascript
var x = 10;
var y = 20;
var z = "The result is: " + x + y; //The result is:1020
```
常见的错误是认为结果应该是 102030：

``` javascript
var x = 10;
var y = 20;
var z = "30";
var result = x + y + z;	//3030
```
JavaScript 从左向右进行编译。

因为 x 和 y 都是数，10 + 20 将被相加。

因为 z 是字符串，30 + "30" 被级联。

**数字字符串**

JavaScript 字符串可以拥有数字内容：

``` javascript
var x = 100;         // x 是数字

var y = "100";       // y 是字符串
```

在所有数字运算中，JavaScript 会尝试将字符串转换为数字：

该例如此运行：

``` javascript
var x = "100";
var y = "10";
var z = x / y;       // z 将是 10
var z = x * y;       // z 将是 1000
var z = x - y;       // z 将是 90
```
但是该例不会如上例般运行：

``` javascript
var x = "100";
var y = "10";
var z = x + y;       // z 不会是 110（而是 10010）
```
JavaScript 用 + 运算符对字符串进行了级联。

**NaN - 非数值**

NaN 属于 JavaScript 保留词，指示某个数不是合法数。

尝试用一个非数字字符串进行除法会得到 NaN（Not a Number）：

``` javascript
var x = 100 / "Apple";  // x 将是 NaN（Not a Number）
```
不过，假如字符串包含数值，则结果将是数：

``` javascript
var x = 100 / "10";     // x 将是 10
```

您可使用全局 JavaScript 函数 isNaN() 来确定某个值是否是数：

``` javascript
var x = 100 / "Apple";
isNaN(x);               // 返回 true，因为 x 不是数
```
要小心 NaN。假如您在数学运算中使用了 NaN，则结果也将是 NaN：

``` javascript
var x = NaN;
var y = 5;
var z = x + y;         // z 将是 NaN
```
结果也许是串连接：

``` javascript
var x = NaN;
var y = "5";
var z = x + y;         // z 将是 NaN5
```
NaN 是数，typeof NaN 返回 number：

``` javascript
typeof NaN;             // 返回 "number"
```
**Infinity**

Infinity （或 -Infinity）是 JavaScript 在计算数时超出最大可能数范围时返回的值。

除以 0（零）也会生成 Infinity：

``` javascript
var x =  2 / 0;          // x 将是 Infinity
var y = -2 / 0;          // y 将是 -Infinity
```
Infinity 是数：typeOf Infinity 返回 number。

``` javascript
typeof Infinity;        // 返回 "number"
```
**十六进制**

JavaScript 会把前缀为 0x 的数值常量解释为十六进制。

``` javascript
var x = 0xFF;             // x 将是 255
```
绝不要用前导零写数字（比如 07）。

一些 JavaScript 版本会把带有前导零的数解释为八进制。

默认地，Javascript 把数显示为十进制小数。

但是您能够使用 toString() 方法把数输出为十六进制、八进制或二进制。

``` javascript
var myNumber = 128;
myNumber.toString(16);     // 返回 80
myNumber.toString(8);      // 返回 200
myNumber.toString(2);      // 返回 10000000
```
**数值可以是对象**

通常 JavaScript 数值是通过字面量创建的原始值：var x = 123

但是也可以通过关键词 new 定义为对象：var y = new Number(123)

``` javascript
var x = 123;
var y = new Number(123);

// typeof x 返回 number
// typeof y 返回 object
```
请不要创建数值对象。这样会拖慢执行速度。

new 关键词使代码复杂化，并产生某些无法预料的结果：

当使用 == 相等运算符时，相等的数看上去相等：

``` javascript
var x = 500;             
var y = new Number(500);

// (x == y) 为 true，因为 x 和 y 有相等的值
```
当使用 === 相等运算符后，相等的数变为不相等，因为 === 运算符需要类型和值同时相等。

``` javascript
var x = 500;             
var y = new Number(500);

// (x === y) 为 false，因为 x 和 y 的类型不同
```
甚至更糟。对象无法进行对比：

``` javascript
var x = new Number(500);             
var y = new Number(500);

// (x == y) 为 false，因为对象无法比较
```

> JavaScript 对象无法进行比较。

### JavaScript 数值方法

**Number 方法和属性**

原始值（比如 3.14 或 2016），无法拥有属性和方法（因为它们不是对象）。

但是通过 JavaScript，方法和属性也可用于原始值，因为 JavaScript 在执行方法和属性时将原始值视作对象。

**toString() 方法**

toString() 以字符串返回数值。

所有数字方法可用于任意类型的数字（字面量、变量或表达式）：

``` javascript
var x = 123;
x.toString();            // 从变量 x 返回 123
(123).toString();        // 从文本 123 返回 123
(100 + 23).toString();   // 从表达式 100 + 23 返回 123
```
**toExponential() 方法**

toExponential() 返回字符串值，它包含已被四舍五入并使用指数计数法的数字。

参数定义小数点后的字符数：

``` javascript
var x = 9.656;
x.toExponential();		 //返回 9.656e+0
x.toExponential(2);     // 返回 9.66e+0
x.toExponential(4);     // 返回 9.6560e+0
x.toExponential(6);     // 返回 9.656000e+0
```
该参数是可选的。如果您没有设置它，JavaScript 不会对数字进行舍入。

**toFixed() 方法**

toFixed() 返回字符串值，它包含了指定位数小数的数字：

``` javascript
var x = 9.656;
x.toFixed(0);           // 返回 10
x.toFixed(2);           // 返回 9.66
x.toFixed(4);           // 返回 9.6560
x.toFixed(6);           // 返回 9.656000
```

toFixed(2) 非常适合处理金钱。

**toPrecision() 方法**

toPrecision() 返回字符串值，它包含了指定长度的数字：

``` javascript
var x = 9.656;
x.toPrecision();        // 返回 9.656
x.toPrecision(2);       // 返回 9.7
x.toPrecision(4);       // 返回 9.656
x.toPrecision(6);       // 返回 9.65600
```
**valueOf() 方法**

valueOf() 以数值返回数值：

``` javascript
var x = 123;
x.valueOf();            // 从变量 x 返回 123
(123).valueOf();        // 从文本 123 返回 123
(100 + 23).valueOf();   // 从表达式 100 + 23 返回 123
```

在 JavaScript 中，数字可以是原始值（typeof = number）或对象（typeof = object）。

在 JavaScript 内部使用 valueOf() 方法可将 Number 对象转换为原始值。

> 所有 JavaScript 数据类型都有 valueOf() 和 toString() 方法。

**把变量转换为数值**

这三种 JavaScript 方法可用于将变量转换为数字：

 - Number() 方法
 - parseInt() 方法
 - parseFloat() 方法

这些方法并非数字方法，而是全局 JavaScript 方法。

**全局方法**

JavaScript 全局方法可用于所有 JavaScript 数据类型。

这些是在处理数字时最相关的方法：

| 方法 | 描述 |
| --- | --- |
| Number() | 返回数字，由其参数转换而来。 |
| parseFloat() | 解析其参数并返回浮点数。 |
| parseInt() | 解析其参数并返回整数。 |

**Number() 方法**

Number() 可用于把 JavaScript 变量转换为数值：

``` javascript
x = true;
Number(x);        // 返回 1
x = false;     
Number(x);        // 返回 0
x = new Date();
Number(x);        // 返回 1404568027739
x = "10"
Number(x);        // 返回 10
x = "10 20"
Number(x);        // 返回 NaN
```

如果无法转换数字，则返回 NaN。

**用于日期的 Number() 方法**

Number() 还可以把日期转换为数字：

``` javascript
Number(new Date("2019-04-15"));    // 返回 1506729600000
```

上面的 Number() 方法返回 1970 年 1 月 1 日至今的毫秒数。

**parseInt() 方法**

parseInt() 解析一段字符串并返回数值。允许空格。只返回首个数字：

``` javascript
parseInt("10");         // 返回 10
parseInt("10.33");      // 返回 10
parseInt("10 20 30");   // 返回 10
parseInt("10 years");   // 返回 10
parseInt("years 10");   // 返回 NaN
```

如果无法转换为数值，则返回 NaN (Not a Number)。

**parseFloat() 方法**

parseFloat() 解析一段字符串并返回数值。允许空格。只返回首个数字：

``` javascript
parseFloat("10");        // 返回 10
parseFloat("10.33");     // 返回 10.33
parseFloat("10 20 30");  // 返回 10
parseFloat("10 years");  // 返回 10
parseFloat("years 10");  // 返回 NaN
```

如果无法转换为数值，则返回 NaN (Not a Number)。

 **数值属性**

| 属性 | 描述 |
| --- | --- |
| MAX_VALUE | 返回 JavaScript 中可能的最大数。 |
| MIN_VALUE | 返回 JavaScript 中可能的最小数。 |
| NEGATIVE_INFINITY | 表示负的无穷大（溢出返回）。 |
| NaN | 表示非数字值（"Not-a-Number"）。 |
| POSITIVE_INFINITY | 表示无穷大（溢出返回）。 |

**数字属性不可用于变量**

数字属性属于名为 number 的 JavaScript 数字对象包装器。

这些属性只能作为 Number.MAX_VALUE 访问。

使用 myNumber.MAX_VALUE，其中 myNumber 是变量、表达式或值，将返回 undefined：

``` javascript
var x = 6;
var y = x.MAX_VALUE;    // y 成为 undefined
```

### JavaScript 数组

**访问完整数组**

通过 JavaScript，可通过引用数组名来访问完整数组：

``` javascript
var cars = ["Saab", "Volvo", "BMW"];
document.getElementById("demo").innerHTML = cars; 
```

**数组元素可以是对象**

JavaScript 变量可以是对象。数组是特殊类型的对象。

正因如此，您可以在相同数组中存放不同类型的变量。

您可以在数组保存对象。您可以在数组中保存函数。你甚至可以在数组中保存数组：

``` javascript
myArray[0] = Date.now;
myArray[1] = myFunction;
myArray[2] = myCars;
```
**遍历数组元素**

使用 Array.foreach() 函数：

``` javascript
<script>
var fruits, text;
fruits = ["Banana", "Orange", "Apple", "Mango"];

text = "<ul>";
fruits.forEach(myFunction);
text += "</ul>";
document.getElementById("demo").innerHTML = text;

function myFunction(value) {
  text += "<li>" + value + "</li>";
} 
</script>
```
**添加数组元素**

向数组添加新元素的最佳方法是使用 push() 方法：

``` javascript
var fruits = ["Banana", "Orange", "Apple", "Mango"];
fruits.push("Lemon");                // 向 fruits 添加一个新元素 (Lemon)
```

也可以使用 length 属性向数组添加新元素：

``` javascript
var fruits = ["Banana", "Orange", "Apple", "Mango"];
fruits[fruits.length] = "Lemon";     // 向 fruits 添加一个新元素 (Lemon)
```

警告！
添加最高索引的元素可在数组中创建未定义的“洞”：

``` javascript
<script>
var fruits, text, fLen, i;
fruits = ["Banana", "Orange", "Apple", "Mango"];
fruits[6] = "Lemon";

fLen = fruits.length;
text = "";
for (i = 0; i < fLen; i++) {
  text += fruits[i] + "<br>";
}
document.getElementById("demo").innerHTML = text;
</script>

/*
输出：
Banana
Orange
Apple
Mango
undefined
undefined
Lemon
*/
```
**关联数组**

很多编程元素支持命名索引的数组。

具有命名索引的数组被称为关联数组（或散列）。

JavaScript 不支持命名索引的数组。

在 JavaScript 中，数组只能使用数字索引。

``` javascript
var person = [];
person[0] = "Bill";
person[1] = "Gates";
person[2] = 62;
var x = person.length;          // person.length 返回 3
var y = person[0];              // person[0] 返回 "Bill"
```
警告！
假如您使用命名索引，JavaScript 会把数组重定义为标准对象。

之后，所有数组的方法和属性将产生非正确结果。

``` javascript
var person = [];
person["firstName"] = "Bill";
person["lastName"] = "Gates";
person["age"] = 62;
var x = person.length;         // person.length 将返回 0
var y = person[0];              // person[0] 将返回 undefined
```

### JavaScript 数组方法

**数组转换为字符串**

JavaScript 方法 toString() 把数组转换为数组值（逗号分隔）的字符串。

``` javascript
var fruits = ["Banana", "Orange", "Apple", "Mango"];

//Banana,Orange,Apple,Mango
document.getElementById("demo").innerHTML = fruits.toString(); 	
```
join() 方法也可将所有数组元素结合为一个字符串。

它的行为类似 toString()，但是您还可以规定分隔符：

``` javascript
var fruits = ["Banana", "Orange","Apple", "Mango"];

//Banana * Orange * Apple * Mango
document.getElementById("demo").innerHTML = fruits.join(" * "); 
```
**Popping 和 Pushing**

在处理数组时，删除元素和添加新元素是很简单的。

Popping 和 Pushing 指的是：

从数组弹出项目，或向数组推入项目。

**Popping**

pop() 方法从数组中删除最后一个元素并返回删除的值：

``` javascript
var fruits = ["Banana", "Orange", "Apple", "Mango"];

//pop() 方法返回“被弹出”的值
var x = fruits.pop();    //从 fruits 删除最后一个元素（"Mango"）  x 的值是 "Mango"
```

**Pushing**

push() 方法（在数组结尾处）向数组添加一个新的元素并返回新数组的长度：

``` javascript
var fruits = ["Banana", "Orange", "Apple", "Mango"];
var x = fruits.push("Kiwi");       //  向 fruits 添加一个新元素     x 的值是 5
```

**位移元素**

位移与弹出等同，但处理首个元素而不是最后一个。

shift() 方法会删除首个数组元素，并把所有其他元素“位移”到更低的索引。

``` javascript
var fruits = ["Banana", "Orange", "Apple", "Mango"];
var x = fruits.shift();            // 从 fruits 删除第一个元素 "Banana"     x的值是 "Banana"
```

unshift() 方法（在开头）向数组添加新元素，返回新数组的长度，并“反向位移”旧元素：


``` javascript
var fruits = ["Banana", "Orange", "Apple", "Mango"];
var x = fruits.unshift("Lemon");    // 向 fruits 添加新元素 "Lemon"   x = 5
```

> 注释：unshift() 方法在 Internet Explorer 8 及更早版本中无法正常工作，会插入值，但返回值将是 undefined。

**删除元素**

既然 JavaScript 数组属于对象，其中的元素就可以使用 JavaScript delete 运算符来删除：

``` javascript
var fruits = ["Banana", "Orange", "Apple", "Mango"];
delete fruits[0];           // 把 fruits 中的首个元素改为 undefined
```
使用 delete 会在数组留下未定义的空洞。请使用 pop() 或 shift() 取而代之。

**拼接数组**

splice() 方法可用于向数组添加新项：

``` javascript
var fruits = ["Banana", "Orange", "Apple", "Mango"];
fruits.splice(2, 0, "Lemon", "Kiwi");  //新数组 Banana,Orange,Apple,Mango
```

 - 第一个参数（2）定义了应添加新元素的位置（拼接）。
 - 第二个参数（0）定义应删除多少元素。
 - 其余参数（“Lemon”，“Kiwi”）定义要添加的新元素。

splice() 方法返回一个包含已删除项的数组：

``` javascript
var fruits = ["Banana", "Orange", "Apple", "Mango"];

//new_arr = [Apple,Mango]
var new_arr = fruits.splice(2, 2, "Lemon", "Kiwi");  //新数组： Banana,Orange,Lemon,Kiwi
```

**使用 splice() 来删除元素**

通过聪明的参数设定，您能够使用 splice() 在数组中不留“空洞”的情况下移除元素：

``` javascript
var fruits = ["Banana", "Orange", "Apple", "Mango"];
fruits.splice(0, 1);        // 删除 fruits 中的第一个元素
```

 - 第一个参数（0）定义新元素应该被添加（接入）的位置。
 - 第二个参数（1）定义应该删除多个元素。

其余参数被省略。没有新元素将被添加。

**合并（连接）数组**

concat() 方法通过合并（连接）现有数组来创建一个新数组：

``` javascript
var myGirls = ["Cecilie", "Lone"];
var myBoys = ["Emil", "Tobias", "Linus"];
var myChildren = myGirls.concat(myBoys);   // 连接 myGirls 和 myBoys
```
concat() 方法不会更改现有数组。它总是返回一个新数组。

> concat() 方法可以使用任意数量的数组参数。

concat() 方法也可以将值作为参数：

``` javascript
var arr1 = ["Cecilie", "Lone"];
var myChildren = arr1.concat(["Emil", "Tobias", "Linus"]); 
```
**裁剪数组**

slice() 方法用数组的某个片段切出新数组。

本例从数组下标1 （"Orange"）开始切出一段数组：

slice() 方法创建新数组。它不会从源数组中删除任何元素。

``` javascript
var fruits = ["Banana", "Orange", "Lemon", "Apple", "Mango"];
var citrus = fruits.slice(1); //citrus = [Orange,Lemon,Apple,Mango] 不改变fruits的值
```
slice() 可接受两个参数，比如 (1, 3)。

该方法会从开始参数选取元素，直到结束参数（不包括）为止。

``` javascript
var fruits = ["Banana", "Orange", "Lemon", "Apple", "Mango"];
var citrus = fruits.slice(1, 3);   //citrus = [Orange,Lemon]  不改变fruits的值
```
如果结束参数被省略，比如第一个例子，则 slice() 会切出数组的剩余部分。

``` javascript

var fruits = ["Banana", "Orange", "Lemon", "Apple", "Mango"];
var citrus = fruits.slice(2); //Lemon,Apple,Mango   不改变fruits的值
```

**自动 toString()**

如果需要原始值，则 JavaScript 会自动把数组转换为字符串。下面两个例子将产生相同的结果：

```javascript
var fruits = ["Banana", "Orange", "Apple", "Mango"];
document.getElementById("demo").innerHTML = fruits.toString(); 
//上下语句等效
document.getElementById("demo").innerHTML = fruits; 
```
### JavaScript 数组排序

**数组排序**

sort() 方法以字母顺序对数组进行排序，修改原数组：

``` javascript
var fruits = ["Banana", "Orange", "Apple", "Mango"];
fruits.sort();   //排序后：Apple,Banana,Mango,Orange
```
**反转数组**

reverse() 方法反转数组中的元素， 修改原数组。

您可以使用它以降序对数组进行排序：

``` javascript
var fruits = ["Banana", "Orange", "Apple", "Mango"];
fruits.sort();            // 对 fruits 中的元素进行排序  排序后：Apple,Banana,Mango,Orange
fruits.reverse();         // 反转元素顺序  反转后：Orange,Mango,Banana,Apple
```
**数字排序**

默认地，sort() 函数按照字符串顺序对值进行排序。

该函数很适合字符串（"Apple" 会排在 "Banana" 之前）。

不过，如果数字按照字符串来排序，则 "25" 大于 "100"，因为 "2" 大于 "1"。

正因如此，sort() 方法在对数值排序时会产生不正确的结果。

通过一个比值函数来修正此问题：

``` javascript
var points = [40, 100, 1, 5, 25, 10];
points.sort(function(a, b){return a - b}); 
```
使用相同的技巧对数组进行降序排序：

``` javascript
var points = [40, 100, 1, 5, 25, 10];
points.sort(function(a, b){return b - a}); 
```

**比值函数**

比较函数的目的是定义另一种排序顺序。

比较函数应该返回一个负，零或正值，这取决于参数：

``` javascript
function(a, b){return a-b}
```

当 `sort()` 函数比较两个值时，会将值发送到比较函数，并根据所返回的值（负、零或正值）对这些值进行排序。

当比较 40 和 100 时，`sort()` 方法会调用比较函数 function(40,100)。

该函数计算 40-100，然后返回 -60（负值）。

排序函数将把 40 排序为比 100 更低的值。

您可以使用下面的代码片段来测试数值和字母排序：

``` html
<button onclick="myFunction1()">以字母顺序排序</button> 
<button onclick="myFunction2()">以数字顺序排序</button>

<p id="demo"></p>

<script>
var points = [40, 100, 1, 5, 25, 10];
document.getElementById("demo").innerHTML = points;

function myFunction1() {
		points.sort();
		document.getElementById("demo").innerHTML  = points; //1,10,100,25,40,5
}
function myFunction2() {
		points.sort(function(a, b){return  a - b});
		document.getElementById("demo").innerHTML = points; //1,5,10,25,40,100
}
</script>
```
**以随机顺序排序数组**

``` javascript
var points = [40, 100, 1, 5, 25, 10];
points.sort(function(a, b){return 0.5 - Math.random()}); 
```

**查找最高（或最低）的数组值**

JavaScript 不提供查找数组中最大或最小数组值的内建函数。

不过，在对数组进行排序之后，您能够使用索引来获得最高或最低值。

升序排序：

``` javascript
var points = [40, 100, 1, 5, 25, 10];
points.sort(function(a, b){return a - b});

// 现在 points[0] 包含最低值
// 而 points[points.length-1] 包含最高值
```
降序排序：

``` javascript
var points = [40, 100, 1, 5, 25, 10];
points.sort(function(a, b){return b - a});

// 现在 points[0] 包含最高值
// 而 points[points.length-1] 包含最低值
```

> 如果仅仅需要找到最高或最低值，对整个数组进行排序是效率极低的方法。

**对数组使用 Math.max()**

使用 Math.max.apply 来查找数组中的最高值：

``` javascript
function myArrayMax(arr) {
    return Math.max.apply(null, arr);
}
```

Math.max.apply([1, 2, 3]) 等于 Math.max(1, 2, 3)。

**对数组使用 Math.min()**

您可以使用 Math.min.apply 来查找数组中的最低值：

``` javascript
function myArrayMin(arr) {
    return Math.min.apply(null, arr);
}
```

Math.min.apply([1, 2, 3]) 等于 Math.min(1, 2, 3)。

**我的 Min / Max JavaScript 方法**

最快的解决方法是使用“自制”方法。

此函数遍历数组，用找到的最高值与每个值进行比较：

实例（查找 Max）

``` javascript
function myArrayMax(arr) {
    var len = arr.length
    var max = -Infinity;
    while (len--) {
        if (arr[len] > max) {
            max = arr[len];
        }
    }
    return max;
}
```

此函数遍历数组，用找到的最低值与每个值进行比较：

实例（查找 Min）

``` javascript
function myArrayMin(arr) {
    var len = arr.length
    var min = Infinity;
    while (len--) {
        if (arr[len] < min) {
            min = arr[len];
        }
    }
    return min;
}
```

**排序对象数组**

JavaScript 数组经常会包含对象：

``` javascript
var cars = [
{type:"Volvo", year:2016},
{type:"Saab", year:2001},
{type:"BMW", year:2010}];
```

即使对象拥有不同数据类型的属性，sort() 方法仍可用于对数组进行排序。

解决方法是通过比较函数来对比属性值：

``` javascript
cars.sort(function(a, b){return a.year - b.year});
```

比较字符串属性会稍复杂：

``` javascript
cars.sort(function(a, b){
	  var x = a.type.toLowerCase();
	  var y = b.type.toLowerCase();
	  if (x < y) {return -1;}
	  if (x > y) {return 1;}
	  return 0;
});
```