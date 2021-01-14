# JavaScript 手册-5 

### JavaScript 提升（Hoisting）

> 提升（Hoisting）是 JavaScript 将声明移至顶部的默认行为。
> Hoisting 是 JavaScript 将所有声明提升到当前作用域顶部的默认行为（提升到当前脚本或当前函数的顶部）。

**JavaScript 声明会被提升**

在 JavaScript 中，可以在使用变量之后对其进行声明。

换句话说，可以在声明变量之前使用它。

例子 1 与例子 2 的结果相同(原因就是Hoisting)：

例子 1

``` javascript
x = 5; // 把 5 赋值给 x
 
elem = document.getElementById("demo"); // 查找元素
elem.innerHTML = x;                     // 在元素中显示 x

var x; // 声明 x
```

例子 2

``` javascript
var x; // 声明 x
x = 5; // 把 5 赋值给 x

elem = document.getElementById("demo"); // 查找元素
elem.innerHTML = x;                     // 在元素中显示 x
```

**let 和 const 关键字**

用 let 或 const 声明的变量和常量不会被提升！

**JavaScript 初始化不会被提升**

> JavaScript 只提升声明，而非初始化。

例子 1 与例子 2 的结果不相同：

例子 1

``` javascript
var x = 5; // 初始化 x
var y = 7; // 初始化 y

elem = document.getElementById("demo"); // 查找元素
elem.innerHTML = x + " " + y;           // 显示 x 和 y         x = 5  y = 7
```

例子 2

``` javascript
var x = 5; // 初始化 x
 
elem = document.getElementById("demo"); // 查找元素
elem.innerHTML = x + " " + y;           // 显示 x 和 y     x = 5  y = undefined
 
var y = 7; // 初始化 y 
```
例2是因为只有声明（var y）被提升到作用域顶部而初始化（x =7）没有被提升到顶部而是被留在原来的位置。

由于 hoisting，y 在其被使用前已经被声明，但是由于未对初始化进行提升，y 的值仍是未定义。

例2的代码实际是下面这样的：

``` javascript
var x = 5; // 初始化 x
var y;	//声明变量y
 
elem = document.getElementById("demo"); // 查找元素

//在javascript中，声明但未初始化的变量的值是undefined，所以此时y = undefined
elem.innerHTML = x + " " + y;           // 显示 x 和 y     x = 5  y = undefined
 
y = 7; // 在此初始化 y 
```

**在顶部声明您的变量！**

Hoisting（对很多开发者来说）是 JavaScript 的一种未知的或被忽视的行为。

如果开发者不理解 hoisting，程序也许会包含 bug（错误）。

为了避免 bug，请始终在每个作用域的开头声明所有变量。

由于这就是 JavaScript 解释代码的方式，请保持这个好习惯。

严格模式中的 JavaScript 不允许在未被声明的情况下使用变量。

### 	JavaScript Use Strict

> "use strict"; 定义 JavaScript 代码应该以“严格模式”执行。

**"use strict" 指令**

"use strict" 是 JavaScript 1.8.5 中的新指令（ECMAScript version 5）。

它不算一条语句，而是一段文字表达式，更早版本的 JavaScript 会忽略它。

"use strict"; 的作用是指示 JavaScript 代码应该以“严格模式”执行。

> 在严格模式中，您无法，例如，使用未声明的变量。

以下版本的浏览器支持严格模式：

 - 版本 10 以后的 IE
 - 版本 4 以后的 Firefox
 - 版本 13 以后的 Chrome
 - 版本 5.1 以后的 Safari
 - 版本 12 以后的 Opera

