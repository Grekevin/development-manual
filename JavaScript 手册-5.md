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

**声明严格模式**

通过在脚本或函数的开头添加 "use strict"; 来声明严格模式。

在脚本开头进行声明，拥有全局作用域（脚本中的所有代码均以严格模式来执行）：

``` javascript
"use strict";
x = 3.14;       // 这会引发错误，因为 x 尚未声明
```

``` javascript
"use strict";
myFunction();

function myFunction() {
     y = 3.14;   // 这会引发错误，因为 y 尚未声明
}
```

在函数中声明严格模式，拥有局部作用域（只有函数中的代码以严格模式执行）：

``` javascript
x = 3.14;       // 这不会引发错误
myFunction();

function  myFunction() {
	"use strict";
	 y = 3.14;   // 这会引发错误
}
```

**"use strict"; 语法**

声明严格模式的语法被设计为兼容更早版本的 JavaScript。

编译 JavaScript 程序中的数值文字（比如 4+5）或字符串文字（"Bill Gates"）不会有负面效果。它只会编译为不存在的变量然后消失。

所有 "use strict"; 只会对“理解”其含义的新编译器产生影响。

**为什么使用严格模式？**

严格模式使我们更容易编写“安全的” JavaScript。

严格模式把之前可接受的“坏语法”转变为真实的错误。

举例来说，在普通的 JavaScript 中，错打变量名会创建新的全局变量。在严格模式中，此举将抛出错误，这样就不可能意外创建全局变量。

在普通 JavaScript 中，如果向不可写属性赋值，开发者不会得到任何错误反馈。

在严格模式中，向不可写的、只能读取的、不存在的属性赋值，或者向不存在的变量或对象赋值，将抛出错误。

**严格模式中不允许的事项**

在不声明变量的情况下使用变量，是不允许的：

``` javascript
"use strict";
x = 3.14;                // 这将引发错误
```


对象也是变量，在不声明对象的情况下使用对象也是不允许的：

``` javascript
"use strict";
x = {p1:10, p2:20};      // 这将引发错误
```

删除变量（或对象）是不允许的：

``` javascript
"use strict";
var x = 3.14;
delete x;                // 这将引发错误
```

删除函数是不允许的：

``` javascript
"use strict";
function x(p1, p2) {}; 
delete x;                 // 这将引发错误
```

重复参数名是不允许的：

``` javascript
"use strict";
function x(p1, p1) {};   // 这将引发错误
```

八进制数值文本是不允许的：

``` javascript
"use strict";
var x = 010;             // 这将引发错误
```

转义字符是不允许的：

``` javascript
"use strict";
var x = \010;            // 这将引发错误
```

写入只读属性是不允许的：

``` javascript
"use strict";
var obj = {};
Object.defineProperty(obj, "x", {value:0, writable:false});

obj.x = 3.14;            // 这将引发错误
```

写入只能获取的属性是不允许的：

``` javascript
"use strict";
var obj = {get x() {return 0} };

obj.x = 3.14;            // 这将引发错误
```

删除不可删除的属性是不允许的：

``` javascript
"use strict";
delete Object.prototype; // 这将引发错误
```

字符串 "eval" 不可用作变量：

``` javascript
"use strict";
var eval = 3.14;         // 这将引发错误
```

字符串 "arguments" 不可用作变量：

``` javascript
"use strict";
var arguments = 3.14;    // 这将引发错误
```

with 语句是不允许的：

``` javascript
"use strict";
with (Math){x = cos(2)}; // 这将引发错误
```

处于安全考虑，不允许 eval() 在其被调用的作用域中创建变量：

``` javascript
"use strict";
eval ("var x = 2");
alert (x);               // 这将引发错误
```

> 在类似 f() 的函数调用中，this 的值是全局对象。在严格模式中，现在它成为了 undefined。

**对未来的保障**

严格模式中不允许使用为未来预留的关键词。它们是：

 - implements
 - interface
 - let
 - package
 - private
 - protected
 - public
 - static
 - yield

``` javascript
"use strict";
var public = 1500;      // 这将引发错误
```

> 警告："use strict" 指令只能在脚本或函数的开头被识别。

### JavaScript this 关键词

**this 是什么？**

JavaScript this 关键词指的是它所属的对象。

它拥有不同的值，具体取决于它的使用位置：

*   在方法中，this 指的是所有者对象。
*   单独的情况下，this 指的是全局对象。
*   在函数中，this 指的是全局对象。
*   在函数中，严格模式下，this 是 undefined。
*   在事件中，this 指的是接收事件的元素。

像 call() 和 apply() 这样的方法可以将 this 引用到任何对象。

**方法中的 this**

在对象方法中，this 指的是此方法的“拥有者”。

在下面的例子中，this 指的是 person 对象。

person 对象是 fullName 方法的拥有者。

``` javascript
<script>
// 创建对象：
var person = {
  firstName: "Bill",
  lastName : "Gates",
  id     : 678,
  fullName : function() {
    return this.firstName + " " + this.lastName;
  }
};

// 显示来自对象的数据：
document.getElementById("demo").innerHTML = person.fullName();	//Bill Gates
</script>
```

**单独的 this**

在单独使用时，拥有者是全局对象，因此 this 指的是全局对象。

在浏览器窗口中，全局对象是 [object Window]：

``` javascript
var x = this;	//this: [object Window]
```

在严格模式中，如果单独使用，那么 this 指的是全局对象 [object Window]：

``` javascript
"use strict";
var x = this;	//this: [object Window]
```

**函数中的 this（默认）**

在 JavaScript 函数中，函数的拥有者默认绑定 this。

因此，在函数中，this 指的是全局对象 [object Window]。

``` javascript
function myFunction() {
  return this;	//this: [object Window]
}
```

**函数中的 this（严格模式）**

JavaScript 严格模式不允许默认绑定。

因此，在函数中使用时，在严格模式下，this 是未定义的（undefined）。

``` javascript
"use strict";
function myFunction() {
  return this;	//this: undefined
}
```

**事件处理程序中的 this**

在 HTML 事件处理程序中，this 指的是接收此事件的 HTML 元素：

``` javascript
<button onclick="this.style.display='none'">
  点击来删除我！
</button>
```

**对象方法绑定**

在此例中，this 是 person 对象（person 对象是该函数的“拥有者”）：

``` javascript
var person = {
  firstName  : "Bill",
  lastName   : "Gates",
  id         : 678,
  myFunction : function() {
    return this;	//[object Object]
  }
};
```

**显式函数绑定**

call() 和 apply() 方法是预定义的 JavaScript 方法。

它们都可以用于将另一个对象作为参数调用对象方法。

在下面的例子中，当使用 person2 作为参数调用 person1.fullName 时，this 将引用 person2，即使它是 person1 的方法：

``` javascript
var person1 = {
  fullName: function() {
    return this.firstName + " " + this.lastName;
  }
}
var person2 = {
  firstName:"Bill",
  lastName: "Gates",
}
person1.fullName.call(person2);  // 会返回 "Bill Gates"
```

### JavaScript Let

ES2015 引入了两个重要的 JavaScript 新关键词：let 和 const。

这两个关键字在 JavaScript 中提供了块作用域（Block Scope）变量（和常量）。

在 ES2015 之前，JavaScript 只有两种类型的作用域：全局作用域和函数作用域。

**全局作用域**

全局（在函数之外）声明的变量拥有全局作用域。

全局变量可以在 JavaScript 程序中的任何位置访问。

``` javascript
var carName = "porsche";

// 此处的代码可以使用 carName

function myFunction() {
  // 此处的代码也可以使用 carName
}
```

**函数作用域**

局部（函数内）声明的变量拥有函数作用域。

局部变量只能在它们被声明的函数内访问。

``` javascript
// 此处的代码不可以使用 carName

function myFunction() {
  var carName = "porsche";
  // 此处的代码可以使用carName
}

// 此处的代码不可以使用 carName
```

**JavaScript 块作用域**

通过 var 关键词声明的变量没有块作用域。

在块 {} 内声明的变量可以从块之外进行访问。

``` javascript
{ 
  var x = 10; 
}
// 此处可以使用 x
```

在 ES2015 之前，JavaScript 是没有块作用域的。

可以使用 let 关键词声明拥有块作用域的变量。

在块 {} 内声明的变量无法从块外访问：

``` javascript
{ 
  let x = 10;
}
// 此处不可以使用 x
```

**重新声明变量**

使用 var 关键字重新声明变量会带来问题。

在块中重新声明变量也将重新声明块外的变量：

``` javascript
var x = 10;
// 此处 x 为 10
{ 
  var x = 6;
  // 此处 x 为 6
}
// 此处 x 为 6
```

使用 let 关键字重新声明变量可以解决这个问题。

在块中重新声明变量不会重新声明块外的变量：

``` javascript
var x = 10;
// 此处 x 为 10
{ 
  let x = 6;
  // 此处 x 为 6
}
// 此处 x 为 10
```

**循环作用域**

在循环中使用 var：

``` javascript
var i = 7;

//在循环中使用的变量使用 var 重新声明了循环之外的变量。
for (var i = 0; i < 10; i++) {
  // 一些语句
}
// 此处，i 为 10
```

在循环中使用 let：

``` javascript
let i = 7;

//在循环中使用的变量使用 let 并没有重新声明循环外的变量。
//如果在循环中用 let 声明了变量 i，那么只有在循环内，变量 i 才是可见的。
for (let i = 0; i < 10; i++) {
  // 一些语句
}
// 此处 i 为 7
```
**函数作用域**

在函数内声明变量时，使用 var 和 let 很相似。

它们都有函数作用域：

``` javascript
function myFunction() {
  var carName = "porsche";   // 函数作用域
}
function myFunction() {
  let carName = "porsche";   // 函数作用域
}
```

**全局作用域**

如果在块外声明声明，那么 var 和 let 也很相似。

它们都拥有全局作用域：

``` javascript
var x = 10;       // 全局作用域
let y = 6;       // 全局作用域
```

**HTML 中的全局变量**

使用 JavaScript 的情况下，全局作用域是 JavaScript 环境。

在 HTML 中，全局作用域是 window 对象。

通过 var 关键词定义的全局变量属于 window 对象：

``` javascript
var carName = "porsche";
// 此处的代码可使用 window.carName
```

通过 let 关键词定义的全局变量不属于 window 对象：

``` javascript
let carName = "porsche";
// 此处的代码不可使用 window.carName
```

**重新声明**

允许在程序的任何位置使用 var 重新声明 JavaScript 变量：

``` javascript
var x = 10;

// 现在，x 为 10
 
var x = 6;

// 现在，x 为 6
```

在相同的作用域，或在相同的块中，通过 let 重新声明一个 var 变量是不允许的：

``` javascript
var x = 10;       // 允许
let x = 6;       // 不允许

{
  var x = 10;   // 允许
  let x = 6;   // 不允许
}
```

在相同的作用域，或在相同的块中，通过 let 重新声明一个 let 变量是不允许的：

``` javascript
let x = 10;       // 允许
let x = 6;       // 不允许

{
  let x = 10;   // 允许
  let x = 6;   // 不允许
}
```

在相同的作用域，或在相同的块中，通过 var 重新声明一个 let 变量是不允许的：

``` javascript
let x = 10;       // 允许
var x = 6;       // 不允许

{
  let x = 10;   // 允许
  var x = 6;   // 不允许
}
```

在不同的作用域或块中，通过 let 重新声明变量是允许的：

``` javascript
let x = 6;       // 允许

{
  let x = 7;   // 允许
}

{
  let x = 8;   // 允许
}
```

