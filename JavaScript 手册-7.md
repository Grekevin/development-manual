

# JavaScript 手册-7

### JavaScript 性能

**减少循环中的活动**

编程经常会用到循环。

循环每迭代一次，循环中的每条语句，包括 for 语句，都会被执行。

能够放在循环之外的语句或赋值会使循环运行得更快。

差的代码：

``` javascript
var i;
for (i = 0; i < arr.length; i++) {}
```

更好的代码：

``` javascript
var i;
var l = arr.length;
for (i = 0; i < l; i++) {}
```

循环每次迭代时，坏代码就会访问数组的 length 属性。

好代码在循环之外访问 length 属性，使循环更快。

**减少 DOM 访问**

与其他 JavaScript 相比，访问 HTML DOM 非常缓慢。

假如您期望访问某个 DOM 元素若干次，那么只访问一次，并把它作为本地变量来使用：

``` javascript
var obj;
obj = document.getElementById("demo");
obj.innerHTML = "Hello"; 
```

**缩减 DOM 规模**

请尽量保持 HTML DOM 中较少的元素数量。

这么做总是会提高页面加载，并加快渲染（页面显示），尤其是在较小的设备上。

每一次试图搜索 DOM（比如 getElementsByTagName）都将受益于一个较小的 DOM。

**避免不必要的变量**

请不要创建不打算存储值的新变量。

通常您可以替换代码：

``` javascript
var fullName = firstName + " " + lastName;
document.getElementById("demo").innerHTML = fullName; 
```

用这段代码：

``` javascript
document.getElementById("demo").innerHTML = firstName + " " + lastName
```

**延迟 JavaScript 加载**

请把脚本放在页面底部，使浏览器首先加载页面。

脚本在下载时，浏览器不会启动任何其他的下载。此外所有解析和渲染活动都可能会被阻塞。

HTTP 规范定义浏览器不应该并行下载超过两种要素。

一个选项是在 script 标签中使用 defer="true"。defer 属性规定了脚本应该在页面完成解析后执行，但它只适用于外部脚本。

如果可能，您可以在页面完成加载后，通过代码向页面添加脚本：

实例

``` javascript
<script>
window.onload = downScripts;

function downScripts() {
    var element = document.createElement("script");
    element.src = "myScript.js";
    document.body.appendChild(element);
}
</script>
```

**避免使用 with**

请避免使用 with 关键词。它对速度有负面影响。它也将混淆 JavaScript 作用域。

严格模式中不允许 with 关键词。

### JavaScript 保留词

[官方文档](https://www.w3school.com.cn/js/js_reserved.asp)

### ECMAScript 5 - JavaScript 5

**ECMAScript 5 是什么？**

ECMAScript 5 也称为 ES5 和 ECMAScript 2009。

**ECMAScript 5 特性**

这些是 2009 年发布的新特性：

 - "use strict" 指令
 - String.trim()
 - Array.isArray()
 - Array.forEach()
 - Array.map()
 - Array.filter()
 - Array.reduce()
 - Array.reduceRight()
 - Array.every()
 - Array.some()
 - Array.indexOf()
 - Array.lastIndexOf()
 - JSON.parse()
 - JSON.stringify()
 - Date.now()
 - 属性 Getter 和 Setter
 - 新的对象属性和方法

**ECMAScript 5 语法更改**

 - 对字符串的属性访问 [ ]
 - 数组和对象字面量中的尾随逗号
 - 多行字符串字面量
 - 作为属性名称的保留字

**新的对象属性和方法**

Object.defineProperty() 是 ES5 中的新对象方法。

它允许您定义对象属性和/或更改属性的值和/或元数据。

``` javascript
// 创建对象：
var person = {
  firstName: "Bill",
  lastName : "Gates",
  language : "NO", 
};

// 更改属性：
Object.defineProperty(person, "language", {
  value: "EN",
  writable : true,
  enumerable : true,
  configurable : true
});

// 枚举属性
var txt = "";
for (var x in person) {
  txt += person[x] + "<br>";
}
document.getElementById("demo").innerHTML = txt;
```

下一个例子是相同的代码，但它隐藏了枚举中的语言属性：

``` javascript
// 创建对象：
var person = {
  firstName: "Bill",
  lastName : "Gates",
  language : "NO", 
};

// 更改属性：
Object.defineProperty(person, "language", {
  value: "EN",
  writable : true,
  enumerable : false,
  configurable : true
});

// 枚举属性
var txt = "";
for (var x in person) {
  txt += person[x] + "<br>";
}
document.getElementById("demo").innerHTML = txt;
```

此例创建一个 setter 和 getter 来确保语言的大写更新：

``` javascript
// 创建对象：
var person = {
  firstName: "Bill",
  lastName : "Gates",
  language : "NO"
};

// 更改属性：
Object.defineProperty(person, "language", {
  get : function() { return language },
  set : function(value) { language = value.toUpperCase()}
});

// 更改语言
person.language = "en";

// 显示语言
document.getElementById("demo").innerHTML = person.language;
```

**ES5 新的对象方法**

``` javascript
// 添加或更改对象属性
Object.defineProperty(object, property, descriptor)

// 添加或更改多个对象属性
Object.defineProperties(object, descriptors)

// 访问属性
Object.getOwnPropertyDescriptor(object, property)

// 将所有属性作为数组返回
Object.getOwnPropertyNames(object)

// 将可枚举属性作为数组返回
Object.keys(object)

// 访问原型
Object.getPrototypeOf(object)

// 防止向对象添加属性
Object.preventExtensions(object)

// 如果可以将属性添加到对象，则返回 true
Object.isExtensible(object)

// 防止更改对象属性（而不是值）
Object.seal(object)

// 如果对象被密封，则返回 true
Object.isSealed(object)

// 防止对对象进行任何更改
Object.freeze(object)

// 如果对象被冻结，则返回 true
Object.isFrozen(object)
```

**对字符串的属性访问**

charAt() 方法返回字符串中指定索引（位置）的字符：

``` javascript
var str = "HELLO WORLD";
str.charAt(0);            // 返回 H
```

ECMAScript 5 允许对字符串进行属性访问：

``` javascript
var str = "HELLO WORLD";
str[0];                   // 返回 H
```

**尾随逗号(Trailing Commas)**

ECMAScript 5 允许在对象和数组定义中使用尾随逗号：

Object 实例

``` javascript
person = {
  firstName: "Bill",
  lastName: " Gates",
  age: 62,
}
```

Array 实例

``` javascript
points = [
  1,
  5,
  10,
  25,
  40,
  100,
];
```

JSON 不允许使用尾随逗号。

JSON 对象：

``` javascript
// 允许：
var person = '{"firstName":"Bill", "lastName":"Gates", "age":62}'
JSON.parse(person)

// 不允许：
var person = '{"firstName":"Bill", "lastName":"Gates", "age":62,}'
JSON.parse(person)
```

JSON 数组：

``` javascript
// 允许：
points = [40, 100, 1, 5, 25, 10]

// 不允许：
points = [40, 100, 1, 5, 25, 10,]
```

**多行字符串**

如果使用反斜杠转义，ECMAScript 5 允许多行的字符串文字（字面量）：

``` javascript
"Hello \
Kitty!";
```

\ 方法可能没有得到普遍的支持。

较旧的浏览器可能会以不同的方式处理反斜杠周围的空格。

一些旧的浏览器不允许 \ 字符后面的空格。

分解字符串文字的一种更安全的方法是使用字符串添加：

``` javascript
"Hello " + 
"Kitty!";
```

**保留字作为属性名称**

ECMAScript 5允许保留字作为属性名称：

对象实例

``` javascript
var obj = {name: "Bill", new: "yes"}
```

### ECMAScript 6 - ECMAScript 2015

**ECMAScript 6 是什么？**

ECMAScript 6 也称为 ES6 和 ECMAScript 2015。

一些人把它称作 JavaScript 6。

本章介绍 ES6 中的一些新特性。

 - JavaScript let
 - JavaScript const
 - 幂 (\*\*)
 - 默认参数值
 - Array.find()
 - Array.findIndex()

**默认参数值**

ES6 允许函数参数具有默认值。

实例

``` javascript
function myFunction(x, y = 10) {
  // y is 10 if not passed or undefined
  return x + y;
}
myFunction(5); // 将返回 15
```

**新的数字属性**

ES6 将以下属性添加到 Number 对象：

 - EPSILON
 - MIN_SAFE_INTEGER
 - MAX_SAFE_INTEGER

实例

``` javascript
var x = Number.EPSILON;	//2.220446049250313e-16
var x = Number.MIN_SAFE_INTEGER;	//-9007199254740991
var x = Number.MAX_SAFE_INTEGER;	//9007199254740991
```

**新的数字方法**

ES6 为 Number 对象添加了 2 个新方法：

 - Number.isInteger()
 - Number.isSafeInteger()

Number.isInteger() 方法
如果参数是整数，则 Number.isInteger() 方法返回 true。

``` javascript
Number.isInteger(10);        // 返回 true
Number.isInteger(10.5);      // 返回 false
```

Number.isSafeInteger() 方法
安全整数是可以精确表示为双精度数的整数。

如果参数是安全整数，则 Number.isSafeInteger() 方法返回 true。

``` javascript
Number.isSafeInteger(10);    // 返回 true
Number.isSafeInteger(12345678901234567890);  // 返回 false
```
新的全局方法
ES6 还增加了 2 个新的全局数字方法：

**isFinite()**

 - isNaN()
 - isFinite() 方法

如果参数为 Infinity 或 NaN，则全局 isFinite() 方法返回 false。

否则返回 true：

``` javascript
isFinite(10/0);       // 返回 false
isFinite(10/1);       // 返回 true
```

**箭头函数（Arrow Function）**

箭头函数允许使用简短的语法来编写函数表达式。

您不需要 function 关键字、return 关键字以及花括号。

``` javascript
// ES5
var x = function(x, y) {
   return x * y;
}

// ES6
const x = (x, y) => x * y;
```

箭头功能没有自己的 this。它们不适合定义对象方法。

箭头功能未被提升。它们必须在使用前进行定义。

使用 const 比使用 var 更安全，因为函数表达式始终是常量值。

如果函数是单个语句，则只能省略 return 关键字和花括号。因此，保留它们可能是一个好习惯：

``` javascript
const x = (x, y) => { return x * y };
```

### JavaScript JSON

