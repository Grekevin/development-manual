* [JavaScript 手册-6](#javascript-手册-6)
		* [JavaScript 调试](#javascript-调试)
		* [JavaScript 样式指南和代码约定](#javascript-样式指南和代码约定)
		* [JavaScript 最佳实践](#javascript-最佳实践)
		* [JavaScript 常见错误](#javascript-常见错误)

# JavaScript 手册-6

### JavaScript 调试

**JavaScript 调试**

在没有调试器的情况下写 JavaScript 是有难度的。

您的代码中也许包含了语法错误，或者逻辑错误，这些都难以诊断。

通常，如果 JavaScript 代码包含错误，也不会发生任何事情。不会有错误消息，并且不会有任何可供查找错误的指示信息。

通常，每当你尝试编写新的 JavaScript 代码，就可能发生错误。

**JavaScript 调试器**

查找编程代码中的错误被称为代码调试。

调试并不简单。但幸运地是，所有现代浏览器都有内置的调试器。

内置的调试器可打开或关闭，强制将错误报告给用户。

通过调试器，您也可以设置断点（代码执行被中断的位置），并在代码执行时检查变量。

通常通过 F12 键启动浏览器中的调试器，然后在调试器菜单中选择“控制台”。

**console.log() 方法**

如果您的浏览器支持调试，那么您可以使用 console.log() 在调试窗口中显示 JavaScript 的值：

``` javascript
<script>
a = 5;
b = 6;
c = a + b;
console.log(c);
</script>
```

**设置断点**

在调试窗口中，您可在 JavaScript 代码中设置断点。

在每个断点中，JavaScript 将停止执行，以使您能够检查 JavaScript 的值。

在检查值之后，您可以恢复代码执行。

**debugger 关键词**

debugger 关键词会停止 JavaScript 的执行，并调用（如果有）调试函数。

这与在调试器中设置断点的功能是一样的。

如果调试器不可用，debugger 语句没有效果。

如果调试器已打开，此代码会在执行第三行之前停止运行。

``` javascript
var x = 15 * 5;
debugger;
document.getElementbyId("demo").innerHTML = x; 
```

### JavaScript 样式指南和代码约定

请始终为您所有的 JavaScript 项目使用相同的代码约定。

**JavaScript 代码约定**

代码约定(Coding conventions)指的是_编程的样式指导方针_。这些原则大体上包括：

*   变量和函数的命名和声明规则
*   使用空格、缩进和注释的规则
*   编程习惯和准则

代码约定_确保质量_：

*   改善代码可读性
*   提升代码可维护性

代码约定可以是团队遵守的成文规则，也可以是您个人的编码习惯。

本页介绍 W3School 使用的通用 JavaScript 代码约定。

**变量名**

在 W3School，我们对标识符名称（变量和函数）使用了驼峰式大小写。

所有名称以字母开头。

``` javascript
firstName = "Bill";
lastName = "Gates";

price = 19.90;
tax = 0.20;

fullPrice = price + (price * tax);
```

**运算符周围的空格**

请始终在运算符（ = + - * / ）周围以及逗号之后添加空格：

``` javascript
var x = y + z;
var values = ["Volvo", "Saab",  "Fiat"];
```

**代码缩进**

请始终使用对代码块缩进使用 4 个空格：

``` javascript
function toCelsius(fahrenheit) {
    return (5 / 9) * (fahrenheit - 32);
}
```

请不要对缩进使用制表符。不同的编辑器对 tab 的解释也不尽相同。

**语句规则**

简单语句的通用规则：

请始终以分号结束单条语句：

``` javascript
var values = ["Volvo", "Saab",  "Fiat"];

var person = {
    firstName: "Bill",
     lastName: "Gates",
    age: 50,
    eyeColor:  "blue"
};
```

针对复杂语句（compound）的通用规则：

 - 请在第一行的结尾处写开括号
 - 请在开括号前使用一个空格
 - 请在新行上写闭括号，不带前导空格
 - 请不要以分号来结束复杂语句

函数：

``` javascript
function toCelsius(fahrenheit) {
    return (5 / 9) * (fahrenheit - 32);
}
```

循环：

``` javascript
for (i = 0; i < 5; i++) {
    x += i;
}
```

条件：

``` javascript
if (time < 20) {
    greeting = "Good day";
} else {
     greeting = "Good evening";
}
```

**对象规则**

针对对象定义的通用规则：

 - 把开括号与对象名放在同一行
 - 在每个属性与其值之间使用冒号加一个空格
 - 不要在最后一个属性值对后面写逗号
 - 请在新行上写闭括号，不带前导空格
 - 请始终以分号结束对象定义

``` javascript
var person = {
    firstName: "Bill",
    lastName: "Gates",
    age: 50,
    eyeColor:  "blue"
};
```

可以对短对象在一行中进行压缩，就像这样：

``` javascript
var person = {firstName:"Bill", lastName:"Gates", age:50, eyeColor:"blue"};
```

**行长度小于 80**

为了提高可读性，请避免每行的长度超过 80 个字符。

如果 JavaScript 语句超过一行的长度，换行的最佳位置是运算符或逗号之后。

``` javascript
document.getElementById("demo").innerHTML =
    "Hello Kitty."; 
```

**命名约定**

请始终对您所有的代码使用相同的命名约定。例如：

*   变量和函数名以_驼峰大小写_来写
*   全局变量使用_大写_（我们不这样做，但是相当普遍）
*   常量（比如 PI）使用_大写_

我们是否应在变量名中使用_连字符_、\_驼峰大小写_或_下划线_吗？

这是程序员们经常讨论的问题。答案取决于这个问题是谁回答的：

*HTML 和 CSS 中的连字符:*

 - HTML5 属性能够以 data- 开头（data-quantity, data-price）。
 - CSS 在 property-names 中使用连字符（font-size）。
 - Hyphens 可被错误地视为减法运算符。JavaScript 命名不允许使用连字符。

*下划线：*

 - 许多程序员喜欢使用下划线（date_of_birth），特别是在 SQL 数据库中。
 - 下划线经常被用在 PHP 参考资料中。

*帕斯卡命名法（PascalCase）：*

 - C 语言程序员经常使用帕斯卡命名法。

*驼峰大小写（camelCase）：*

 - JavaScript 本身、jQuery 以及其他 JavaScript 库使用驼峰大小写。
 - JavaScript 命名请不要以 $ 符号开头。此举会引起 JavaScript 库名称冲突。

**在 HTML 中加载 JavaScript**

使用简单的语法来加载外部脚本（type 属性不是必需的）：

``` html
<script src="myscript.js"></script>
```

**访问 HTML 元素**

使用“不整洁的” HTML 样式的后果，也许是导致 JavaScript 错误。

这两条 JavaScript 语句会产生不同的结果：

``` javascript
var obj = getElementById("Demo")

var obj = getElementById("demo") 
```

如果可能，请在 HTML 中使用相同的命名约定（就像 JavaScript 那样）。

**文件扩展名**

HTML 文件应该使用 .html 扩展名（而非 .htm）。

CSS 文件应该使用 .css 扩展名。

JavaScript 文件应该使用 .js 扩展名。

**使用小写文件名**

大多数 web 服务器（Apache、Unix）对文件名的大小写敏感：

 - london.jpg 无法视作 London.jpg 进行访问。

其他 web 服务器（微软的 IIS）对大小写不敏感：

 - london.jpg 能够以 London.jpg 或 london.jpg 来访问。

如果您混合使用大小写，则必须严格保持连续和一致。

如果您将站点从大小写不敏感的服务器转移至对大小写敏感的服务器，即使这种小错误也可能破坏您的网站。

为了避免这些问题，请始终使用小写文件名（如果可能）。

**性能**

计算机不会使用代码约定。大部分规则对程序的执行影响很小。

缩进和额外的空格对小段脚本并不重要。

对于开发中的脚本，应该优先考虑可读性。应该缩小更大型的生产脚本。

### JavaScript 最佳实践

> 请避免全局变量、new、===、eval()

**避免全局变量**

请尽量少地使用全局变量。

它包括所有的数据类型、对象和函数。

全局变量和函数可被其他脚本覆盖。

请使用局部变量替代，并学习如何使用闭包。

**始终声明局部变量**

所有在函数中使用的变量应该被声明为局部变量。

局部变量未经声明关键字声明，将变成全局变量。

严格模式不允许使用未声明的变量。

**在顶部声明**

一项好的编码习惯是把所有声明放在每段脚本或函数的顶部。

这么做的好处是：

 - 获得更整洁的代码
 - 提供了查找局部变量的好位置
 - 更容易避免不需要的全局变量
 - 减少不需要的重新声明的可能性

``` javascript
// 在顶部声明
var firstName, lastName, price, discount, fullPrice;

// 稍后使用
firstName = "Bill";
lastName = "Gates";

price = 19.90;
discount = 0.10;

fullPrice = price * 100 / discount;
```

也可以用于循环变量：

``` javascript
// 在顶部声明
var i;

// 稍后使用
for (i = 0; i < 5; i++)  {}
```

默认地，JavaScript 会将所有声明移至顶部（JavaScript hoisting）。

**初始化变量**

在您声明变量时对其进行初始化是个好习惯。

这么做的好处是：

 - 更整洁的代码
 - 在单独的位置来初始化变量
 - 避免未定义值

``` javascript
// 在开头进行声明和初始化
var firstName = "",
    lastName  = "",
    price = 0,
    discount = 0,
    fullPrice  = 0,
    myArray = [],
    myObject = {};
```

变量初始化使我们能够了解预期用途和预期的数据类型。

**请不要声明数值、字符串或布尔对象**

请始终将数值、字符串或布尔值视作原始值。而非对象。

如果把这些类型声明为对象，会拖慢执行速度，并产生讨厌的副作用：

``` javascript
var x = "Bill";             
var y = new String("Bill");
(x === y) // 结果为 false，因为 x 是字符串，而 y 是对象。
```

或者甚至更糟：

``` javascript
var x = new String("Bill");             
var y = new String("Bill");
(x == y) // 结果是 false，因为你无法比较对象。
```

**请勿使用 new Object()**

 - 请使用 {} 来代替 new Object()
 - 请使用 "" 来代替 new String()
 - 请使用 0 来代替 new Number()
 - 请使用 false 来代替 new Boolean()
 - 请使用 [] 来代替 new Array()
 - 请使用 /()/ 来代替 new RegExp()
 - 请使用 function (){}来代替 new Function()

``` javascript
var x1 = {};           // 新对象
var x2 = "";           // 新的原始字符串值
var x3 = 0;            // 新的原始数值
var x4 = false;        // 新的原始布尔值
var x5 = [];           // 新的数组对象
var x6 = /()/;         // 新的正则表达式
var x7 = function(){}; // 新的函数对象
```

**意识到自动类型转换**

请意识到数值会被意外转换为字符串或 NaN（Not a Number）。

JavaScript 属于松散类型。变量可包含不同的数据类型，并且变量能够改变其数据类型：

``` javascript
var x = "Hello";     // typeof x 为字符串
x = 5;               // 把 typeof x 更改为数值
```

如果进行数学运算，JavaScript 能够将数值转换为字符串：

``` javascript
var x = 5 + 7;       // x.valueOf() 是 12,  typeof x 是数值
var x = 5 + "7";     // x.valueOf() 是 57,  typeof x 是字符串
var x = "5" + 7;     // x.valueOf() 是 57,  typeof x 是字符串
var x = 5 - 7;       // x.valueOf() 是 -2,  typeof x 是数值
var x = 5 - "7";     // x.valueOf() 是 -2,  typeof x 是数值
var x = "5" - 7;     // x.valueOf() 是 -2,  typeof x 是数值
var x = 5 - "x";     // x.valueOf() 是 NaN, typeof x 是数值
```

用字符串减去字符串，不会产生错误而是返回 NaN（Not a Number）：

``` javascript
"Hello" - "Dolly"    // 返回 NaN
```

**使用 === 比较**

== 比较运算符总是在比较之前进行类型转换（以匹配类型）。

=== 运算符会强制对值和类型进行比较：

``` javascript
0 == "";        // true
1 == "1";       // true
1 == true;      // true

0 === "";       // false
1 === "1";      // false
1 === true;     // false
```

**使用 Parameter Defaults**

如果调用函数时缺少一个参数，那么这个缺失参数的值会被设置为 undefined。

undefined 值会破坏您的代码。为参数设置默认值是一个好习惯。

``` javascript
function myFunction(x, y) {
    if (y === undefined) {
        y = 0;
    }
}
```

**用 default 来结束 switch**

请使用使用 default 来结束您的 switch 语句。即使您认为没有这个必要。

**避免使用 eval()**

eval() 函数用于将文本作为代码来允许。在几乎所有情况下，都没有必要使用它。

因为允许任意代码运行，它同时也意味着安全问题。

### JavaScript 常见错误

**意外使用赋值运算符**

如果程序员在 if 语句中意外使用赋值运算符（=）而不是比较运算符（===），JavaScript 程序可能会产生一些无法预料的结果。

这条 if 语句返回 false（正如预期），因为 x 不等于 10：

``` javascript
var x = 0;
if (x == 10) 
```

这条 if 语句返回 true（也许不像预期），因为 10 为 true：

``` javascript
var x = 0;
if (x = 10) 
```

这条 if 语句返回 false（也许不像预期），因为 0 为 false：

``` javascript
var x = 0;
if (x = 0) 
```
赋值总是返回赋值的值。

**期望松散的比较**

在常规比较中，数据类型不重要。这条 if 语句返回 true：

``` javascript
var x = 10;
var y = "10";
if (x == y) 
```

在严格比较中，数据类型确实重要。这条 if 语句返回 false：

``` javascript
var x = 10;
var y = "10";
if (x === y) 
```

有一个常见的错误是忘记在 switch 语句中使用严格比较：

这条 switch 语句会显示提示框：

``` javascript
var x = 10;
switch(x) {
    case 10: alert("Hello");
}
```

这条 switch 语句不会显示提示框：

``` javascript
var x = 10;
switch(x) {
    case "10": alert("Hello");
}
```

**令人困惑的加法和级联**

加法用于加数值。

级联（Concatenation）用于加字符串。

在 JavaScript 中，这两种运算均使用相同的 + 运算符。

正因如此，将数字作为数值相加，与将数字作为字符串相加，将产生不同的结果：

``` javascript
var x = 10 + 5;          // x 中的结果是 15
var x = 10 + "5";         // x 中的结果是　"105"
```

如果是两个变量相加，很难预测结果：

``` javascript
var x = 10;
var y = 5;
var z = x + y;            // z 中的结果是 15

var x = 10;
var y = "5";
var z =  x + y;            // z 中的结果是 "105"
```

**令人误解的浮点**

JavaScript 中的数字均保存为 64 位的浮点数（Floats）。

所有编程语言，包括 JavaScript，都存在处理浮点值的困难：

``` javascript
var x = 0.1;
var y = 0.2;
var z = x + y             // z 中的结果并不是 0.3
```

为了解决上面的问题，请使用乘除运算：

``` javascript
var z = (x * 10 + y * 10) / 10;       // z 中的结果将是 0.3
```

**对 JavaScript 字符串换行**

JavaScript 允许您把一条语句换行为两行：

``` javascript
var x =
"Hello World!";
```

但是，在字符串中间来换行是不对的：

``` javascript
var x = "Hello
World!";
```
如果必须在字符串中换行，则必须使用反斜杠：

``` javascript
var x = "Hello \
World!";
```
**错位的分号**

因为一个错误的分号，此代码块无论 x 的值如何都会执行：

``` javascript
if (x == 19);
{
     // code block
}
```

**对 return 语句进行换行**

在一行的结尾自动关闭语句是默认的 JavaScript 行为。

正因如此，下面两个例子返回相同的结果：

例子 1

``` javascript
function myFunction(a) {
    var power = 10  
    return a * power
}
```

例子 2

``` javascript
function myFunction(a) {
    var power = 10;
    return a * power;
}
```

JavaScript 也允许您将一条语句换行为两行。

正因如此，例子 3 也将返回相同的结果：

例子 3

``` javascript
function myFunction(a) {
    var
    power = 10;  
    return a * power;
}
```

但是，如果把 return 语句换行为两行会发生什么呢：

例子 4

``` javascript
function myFunction(a) {
    var
    power = 10;  
    return
    a * power;
}
```

此函数将返回 undefined！

为什么呢？因为 JavaScript 认为你的意思是：

``` javascript
function myFunction(a) {
     var
    power = 10;  
    return;
    a * power;
}
```

**解释**

如果某条语句是不完整的：

``` javascript
var
```

JavaScript 将通过读取下一行来完成这条语句：

``` javascript
power = 10;
```

但是由于这条语句是完整的：

``` javascript
return
```

JavaScript 会自动关闭该语句：

``` javascript
return;
```

发生这种情况是因为，在 JavaScript 中，用分号来关闭（结束）语句是可选的。

JavaScript 会在行末关闭 return 语句，因为它本身就是一条完整的语句。

所以，绝不要对 return 语句进行换行。

**通过命名索引来访问数组**

很多编程语言支持带有命名索引的数组。

带有命名索引的数组被称为关联数组（或散列）。

JavaScript 不支持带有命名索引的数组。

在 JavaScript 中，数组使用数字索引：

``` javascript
var person = [];
person[0] = "Bill";
person[1] = "Gates";
person[2] = 46;
var x = person.length;          // person.length 将返回 3
var y = person[0];              // person[0] 将返回 "John"
```

在 JavaScript 中，对象使用命名索引。

如果您使用命名索引，那么在访问数组时，JavaScript 会将数组重新定义为标准对象。

在自动重定义之后，数组方法或属性将产生未定义或非正确的结果：

``` javascript
var person = [];
person["firstName"] = "Bill";
person["lastName"] = "Gates";
person["age"] = 46;
var x = person.length;         // person.length 将返回 0
var y = person[0];              // person[0] 将返回 undefined
```

**用逗号来结束定义**

对象和数组定义中的尾随逗号在 ECMAScript 5 中是合法的。

对象实例：

``` javascript
person = {firstName:"Bill", lastName:"Gates", age:62,}
```

数组实例：

``` javascript
points = [35, 450, 2, 7, 30, 16,];
```

警告！！
Internet Explorer 8 会崩溃。

JSON 不允许尾随逗号。

JSON:

``` javascript
person = {firstName:"Bill", lastName:"Gates", age:62}
```

JSON:

``` javascript
points = [35, 450, 2, 7, 30, 16];
```

**Undefined 不是 Null**

JavaScript 对象、变量、属性和方法可以是未定义的。

此外，空的 JavaScript 对象的值可以为 null。

这可能会使测试对象是否为空变得有点困难。

您可以通过测试类型是否为 undefined，来测试对象是否存在：

``` javascript
if (typeof myObj === "undefined")
```

但是您无法测试对象是否为 null，因为如果对象未定义，将抛出错误：

不正确的：

``` javascript
if (myObj === null)
```

要解决此问题，必须测试对象是否为 null，而不是未定义。

但这仍然会引发错误：

不正确的：

``` javascript
if (myObj !== null && typeof myObj !== "undefined")
```

因此，在测试非 null 之前，必须先测试未定义：

正确的：

``` javascript
if (typeof myObj !== "undefined" && myObj !== null)
```

**期望块级范围**

JavaScript 不会为每个代码块创建新的作用域。

很多编程语言都是如此，但是 JavaScript 并非如此。

认为这段代码会返回 undefined，是新的 JavaScript 开发者的常见错误：

``` javascript
console.log(i); // Return undefined

for (var i = 0; i < 10; i++) {
  // 代码块
}
return i;	//10
```

