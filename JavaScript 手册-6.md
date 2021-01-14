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

