
# JS 函数
## JavaScript 函数定义

JavaScript 函数是通过 function 关键词定义的。

您可以使用函数声明或函数表达式。

### 函数声明

声明函数语法：

``` javascript
function functionName(parameters) {
   要执行的代码
}
```

被声明的函数不会直接执行，只有当它们被调用时才会执行。

示例：

``` javascript
function myFunction(a, b) {
     return a * b;
}
```
> 分号用于分隔可执行的 JavaScript 语句。
> 由于函数声明不是可执行的语句，以分号结尾并不常见。

### 函数表达式
JavaScript 函数也可以使用表达式来定义。

函数表达式可以在变量中存储：

``` javascript
var x = function (a, b) {return a * b};
```

在变量中保存函数表达式之后，此变量可用作函数：

``` javascript
var x = function (a, b) {return a * b};
var z = x(4, 3);
```

上面的函数实际上是一个匿名函数（没有名称的函数）。

存放在变量中的函数不需要函数名。他们总是使用变量名调用。

上面的函数使用分号结尾，因为它是可执行语句的一部分。

### Function() 构造器

正如您在之前的例子中看到的，JavaScript 函数是通过 function 关键词定义的。

函数也可以通过名为 Function() 的内建 JavaScript 函数构造器来定义。

``` javascript
var myFunction = new Function("a", "b", "return a * b");

var x = myFunction(4, 3);
```
您实际上无需使用函数构造器。上面的例子这么写也是一样的：

``` javascript
var myFunction = function (a, b) {return a * b};
var x = myFunction(4, 3);
```

> 大多数情况下，您可以避免在 JavaScript 中使用 new 关键词。

### 函数提升

Hoisting 是 JavaScript 将声明移动到当前作用域顶端的默认行为。

Hoisting 应用于变量声明和函数声明。

正因如此，JavaScript 函数能够在声明之前被调用：

``` javascript
myFunction(5);

 function myFunction(y) {
     return y * y;
}
```

> 使用表达式定义的函数不会被提升。

### 自调用函数

函数表达式可以作为“自调用”。

自调用表达式是自动被调用（开始）的，在不进行调用的情况下。

函数表达式会自动执行，假如表达式后面跟着 ()。

无法对函数声明进行自调用。

需要在函数周围添加括号，以指示它是一个函数表达式：

``` javascript
(function () {
    var x = "Hello!!";      //我会调用我自己
})();
```
上面的函数实际上是一个匿名的自调用函数（没有名称的函数）。

### 函数可用作值

JavaScript 函数可被用作值：

``` javascript
function myFunction(a, b) {
    return a * b;
}

var x = myFunction(4, 3);
```

JavaScript 函数可用在表达式中：

``` javascript
function myFunction(a, b) {
    return a * b;
}

var x = myFunction(4, 3) * 2;
```

### 函数是对象

JavaScript 中的 typeof 运算符会为函数返回 "function"。

但是最好是把 JavaScript 函数描述为对象。

JavaScript 函数都有属性和方法。

arguments.length 会返回函数被调用时收到的参数数目：

``` javascript
function myFunction(a, b) {
    return arguments.length;
}
```
toString() 方法以字符串返回函数：

``` javascript
function myFunction(a, b) {
    return a * b;
}

var txt = myFunction.toString();
```

 - 定义为对象属性的函数，被称为对象的方法。
 - 为创建新对象而设计的函数，被称为对象构造函数（对象构造器）。

