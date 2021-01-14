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