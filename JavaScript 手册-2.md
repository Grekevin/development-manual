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

