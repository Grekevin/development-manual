
# JS 对象

## JavaScript 对象定义

在 JavaScript 中，对象是王。如果您理解了对象，就理解了 JavaScript。

在 JavaScript 中，几乎“所有事物”都是对象。

 - 布尔是对象（如果用 new 关键词定义）
 - 数字是对象（如果用 new 关键词定义）
 - 字符串是对象（如果用 new 关键词定义）
 - 日期永远都是对象
 - 算术永远都是对象
 - 正则表达式永远都是对象
 - 数组永远都是对象
 - 函数永远都是对象
 - 对象永远都是对象

所有 JavaScript 值，除了原始值，都是对象。

### JavaScript 原始值

原始值指的是没有属性或方法的值。

原始数据类型指的是拥有原始值的数据。

JavaScript 定义了 5 种原始数据类型：

 - string
 - number
 - boolean
 - null
 - undefined

原始值是一成不变的（它们是硬编码的，因此不能改变）。

假设 x = 3.14，您能够改变 x 的值。但是您无法改变 3.14 的值。

| 值 | 类型 | 注释 |
| --- | --- | --- |
| "Hello" | string | "Hello" 始终是 "Hello" |
| 3.14 | number | 3.14 始终是 3.14 |
| true | boolean | true 始终是 true |
| false | boolean | false 始终是 false |
| null | null | (object) null 始终是 null |
| undefined | undefined | undefined 始终是 undefined |

### 对象是包含变量的变量

JavaScript 变量能够包含单个的值：

``` javascript
var person = "Bill Gates";
```

对象也是变量。但是对象能够包含很多值。

值按照名称 : 值对的形式编写（名称和值以冒号分隔）。

``` javascript
var person = {firstName:"Bill", lastName:"Gates", age:62, eyeColor:"blue"};
```

JavaScript 对象是命名值的集合。

### 对象属性

JavaScript 对象中的命名值，被称为_属性_。

| 属性 | 值 |
| --- | --- |
| firstName | Bill |
| lastName | Gates |
| age | 62 |
| eyeColor | blue |

以名称值对书写的对象类似于：

*   PHP 中的关联数组
*   Python 中的字典
*   C 中的哈希表
*   Java 中的哈希映射
*   Ruby 和 Perl 中的散列

### 对象方法

方法是可以在对象上执行的_动作_。

对象属性可以是原始值、其他对象以及函数。

对象方法是包含函数定义的对象属性。

| 属性 | 值 |
| --- | --- |
| firstName | Bill |
| lastName | Gates |
| age | 62 |
| eyeColor | blue |
| fullName | function() {return this.firstName + " " + this.lastName;} |

JavaScript 对象是被称为属性和方法的命名值的容器。

### 创建 JavaScript 对象

通过 JavaScript，您能够定义和创建自己的对象。

有不同的方法来创建对象：

 - 定义和创建单个对象，使用对象文字。
 - 定义和创建单个对象，通过关键词 new。
 - 定义对象构造器，然后创建构造类型的对象。

在 ECMAScript 5 中，也可以通过函数 Object.create() 来创建对象。

#### 使用对象字面量
这是创建对象最简单的方法。

使用对象文字，您可以在一条语句中定义和创建对象。

对象文字指的是花括号 {} 中的名称:值对（比如 age:62）。

下面的例子创建带有四个属性的新的 JavaScript 对象：

``` javascript
var person = {firstName:"Bill", lastName:"Gates", age:62, eyeColor:"blue"};
```

空格和折行不重要。对象定义可横跨多行：

``` javascript
var person = {
    firstName:"Bill",
    lastName:"Gates",
    age:62,
    eyeColor:"blue"
};
```

