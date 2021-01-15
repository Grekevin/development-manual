* [JS 对象](#js-对象)
	* [JavaScript 对象定义](#javascript-对象定义)
		* [JavaScript 原始值](#javascript-原始值)
		* [对象是包含变量的变量](#对象是包含变量的变量)
		* [对象属性](#对象属性)
		* [对象方法](#对象方法)
		* [创建 JavaScript 对象](#创建-javascript-对象)
			* [使用对象字面量](#使用对象字面量)
			* [使用 JavaScript 关键词 new](#使用-javascript-关键词-new)
		* [JavaScript 对象是易变的](#javascript-对象是易变的)
	* [JavaScript 对象属性](#javascript-对象属性)
		* [访问 JavaScript 属性](#访问-javascript-属性)
		* [JavaScript for...in 循环](#javascript-forin-循环)
		* [添加新属性](#添加新属性)
		* [删除属性](#删除属性)
		* [属性值](#属性值)
		* [原型属性](#原型属性)

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

#### 使用 JavaScript 关键词 new
下面的例子也创建了带有四个属性的新的 JavaScript 对象：

``` javascript
var person = new Object();
person.firstName = "Bill";
person.lastName = "Gates";
person.age = 50;
person.eyeColor = "blue"; 
```

上面的两个例子结果是一样的。无需使用 new Object()。

出于简易性、可读性和执行速度的考虑，请使用第一种创建方法（对象文字方法）。

### JavaScript 对象是易变的

对象是易变的：它们通过引用来寻址，而非值。

如果 person 是一个对象，下面的语句不会创建 person 的副本：

``` javascript
var x = person;  // 这不会创建 person 的副本。
```

对象 x 并非 person 的副本。它就是 person。x 和 person 是同一个对象。

对 x 的任何改变都将改变 person，因为 x 和 person 是相同的对象。

``` javascript
var person = {firstName:"Bill", lastName:"Gates", age:62, eyeColor:"blue"}
 
var x = person;
x.age = 10;           // 这将同时改变 both x.age 和 person.age
```

> 注释：JavaScript 变量不是易变的。只有 JavaScript 对象如此。

## JavaScript 对象属性

属性指的是与 JavaScript 对象相关的值。

JavaScript 对象是无序属性的集合。

属性通常可以被修改、添加和删除，但是某些属性是只读的。

### 访问 JavaScript 属性

访问对象属性的语法是：

``` javascript
_objectName_._property_           // person.age

person.firstname + " is " + person.age + " years old.";
```

或者：

``` javascript
_objectName_["_property_"]       // person["age"]

person["firstname"] + " is " + person["age"] + " years old.";
```

或者：

``` javascript
_objectName_[_expression_]       // x = "age"; person[x]
```
表达式必须计算为属性名。

### JavaScript for...in 循环
JavaScript for...in 语句遍历对象的属性。

``` javascript
for (variable in object) {
    要执行的代码
}
```

for...in 循环中的代码块会为每个属性执行一次。

循环对象的属性：

var person = {fname:"Bill", lname:"Gates", age:62}; 

``` javascript
for (x in person) {
    txt += person[x];
}
```

### 添加新属性
您可以通过简单的赋值，向已存在的对象添加新属性。

假设 person 对象已存在 - 那么您可以为其添加新属性：

``` javascript
person.nationality = "English";
```

您不能使用预留词作为属性名（或方法名）。请使用 JavaScript 命名规则。

### 删除属性
delete 关键词从对象中删除属性：

``` javascript
var person = {firstName:"Bill", lastName:"Gates", age:62, eyeColor:"blue"};
delete person.age;   // 或 delete person["age"];
```

 - delete 关键词会同时删除属性的值和属性本身。
 - 删除完成后，属性在被添加回来之前是无法使用的。
 - delete 操作符被设计用于对象属性。它对变量或函数没有影响。
 - delete 操作符不应被用于预定义的 JavaScript 对象属性。这样做会使应用程序崩溃。

### 属性值

所有属性都有名称。此外它们还有值。

值是属性的特性之一。

其他特性包括：可列举、可配置、可写。

这些特性定义了属性被访问的方式（是可读的还是可写的？）

在 JavaScript 中，所有属性都是可读的，但是只有值是可修改的（只有当属性为可写时）。

（ECMAScript 5 拥有获取和设置所有属性特性的方法）

### 原型属性

JavaScript 对象继承了它们的原型的属性。

delete 关键词不会删除被继承的属性，但是如果您删除了某个原型属性，则将影响到所有从原型继承的对象。

## JavaScript 对象方法

### JavaScript 方法

JavaScript 方法是能够在对象上执行的动作。

JavaScript 方法是包含函数定义的属性。

| 属性 | 值 |
| --- | --- |
| firstName | Bill |
| lastName | Gates |
| age | 62 |
| eyeColor | blue |
| fullName | function() {return this.firstName + " " + this.lastName;} |

方法是存储为对象属性的函数。

### this 关键词

在 JavaScript 中，被称为 this 的事物，指的是拥有该 JavaScript 代码的对象。

this 的值，在函数中使用时，是“拥有”该函数的对象。

请注意 this 并非变量。它是关键词。您无法改变 this 的值。

### 访问对象方法

请使用如下语法创建对象方法：

``` javascript
methodName : function() { 代码行 }
```

请通过如下语法来访问对象方法：

``` javascript
objectName.methodName()
```

您通常会把 fullName() 描述为 person 对象的方法，把 fullName 描述为属性。

fullName 属性在被通过 () 调用后会以函数形式执行。

此例访问 person 对象的 fullName() 方法：

``` javascript
name = person.fullName();
```

如果您访问 fullName 属性时没有使用 ()，则将返回函数定义：

``` javascript
name = person.fullName;
```

### 使用内建方法

此例使用 String 对象的 toUpperCase() 方法，把文本转换为大写：

``` javascript
var message = "Hello world!";
var x = message.toUpperCase();
```

x 的值，在以上代码执行后将是：

``` javascript
HELLO WORLD!
```

### 添加新的方法

向对象添加方法是在构造器函数内部完成的：

``` javascript
function person(firstName, lastName, age, eyeColor) {
    this.firstName = firstName;  
    this.lastName = lastName;
    this.age = age;
    this.eyeColor = eyeColor;
    this.changeName = function (name) {
        this.lastName = name;
    };
}
changeName() 函数 name 的值赋给了 person 的 lastName 属性。
```

现在您可以尝试：

``` javascript
myMother.changeName("Jobs");
```

通过用 myMother “替代” this，JavaScript 清楚您指的是哪个 person。

## JavaScript 对象访问器

### JavaScript 访问器（Getter 和 Setter）

ECMAScript 5 (2009) 引入了 Getter 和 Setter。

Getter 和 Setter 允许您定义对象访问器（被计算的属性）。

### JavaScript Getter（get 关键词）

本例使用 lang 属性来获取 language 属性的值。

``` javascript
// 创建对象：
var person = {
  firstName: "Bill",
  lastName : "Gates",
  language : "en",
  get lang() {
    return this.language;
  }
};

// 使用 getter 来显示来自对象的数据：
document.getElementById("demo").innerHTML = person.lang;
```

### JavaScript Setter（set 关键词）

本例使用 lang 属性来设置 language 属性的值。

``` javascript
var person = {
  firstName: "Bill",
  lastName : "Gates",
  language : "",
  set lang(lang) {
    this.language = lang;
  }
};

// 使用 setter 来设置对象属性：
person.lang = "en";

// 显示来自对象的数据：
document.getElementById("demo").innerHTML = person.language;
```

### JavaScript 函数还是 Getter？

下面两个例子的区别在哪里？

例子 1

``` javascript
var person = {
  firstName: "Bill",
  lastName : "Gates",
  fullName : function() {
    return this.firstName + " " + this.lastName;
  }
};

// 使用方法来显示来自对象的数据：
document.getElementById("demo").innerHTML = person.fullName();
```

亲自试一试

``` javascript
var person = {
  firstName: "Bill",
  lastName : "Gates",
  get fullName() {
    return this.firstName + " " + this.lastName;
  }
};

// 使用 getter 来显示来自对象的数据：
document.getElementById("demo").innerHTML = person.fullName;
```

例子 1 以函数形式访问 fullName：person.fullName()。

例子 2 以属性形式访问 fullName：person.fullName。

第二个例子提供了更简洁的语法。

### 数据质量

使用 getter 和 setter 时，JavaScript 可以确保更好的数据质量。

在本例中，使用 lang 属性以大写形式返回 language 属性的值：

``` javascript
// Create an object:
var person = {
  firstName: "Bill",
  lastName : "Gates",
  language : "en",
  get lang() {
    return this.language.toUpperCase();
  }
};

// 使用 getter 来显示来自对象的数据：
document.getElementById("demo").innerHTML = person.lang;
```

在本例中，使用 lang 属性将大写值存储在 language 属性中：

``` javascript
var person = {
  firstName: "Bill",
  lastName : "Gates",
  language : "",
  set lang(lang) {
    this.language = lang.toUpperCase();
  }
};

// 使用 getter 来设置对象属性：
person.lang = "en";

// 显示来自对象的数据：
document.getElementById("demo").innerHTML = person.language;
```

### 为什么使用 Getter 和 Setter？

 - 它提供了更简洁的语法
 - 它允许属性和方法的语法相同
 - 它可以确保更好的数据质量
 - 有利于后台工作

### 一个计数器实例

``` javascript
var obj = {
  counter : 0,
  get reset() {
    this.counter = 0;
  },
  get increment() {
    this.counter++;
  },
  get decrement() {
    this.counter--;
  },
  set add(value) {
    this.counter += value;
  },
  set subtract(value) {
    this.counter -= value;
  }
};

// 操作计数器：
obj.reset;
obj.add = 5;
obj.subtract = 1;
obj.increment;
obj.decrement;
Object.defineProperty()
```

Object.defineProperty() 方法也可用于添加 Getter 和 Setter：

``` javascript
// 定义对象
var obj = {counter : 0};

// 定义 setters
Object.defineProperty(obj, "reset", {
  get : function () {this.counter = 0;}
});
Object.defineProperty(obj, "increment", {
  get : function () {this.counter++;}
});
Object.defineProperty(obj, "decrement", {
  get : function () {this.counter--;}
});
Object.defineProperty(obj, "add", {
  set : function (value) {this.counter += value;}
});
Object.defineProperty(obj, "subtract", {
  set : function (value) {this.counter -= value;}
});

// 操作计数器：
obj.reset;
obj.add = 5;
obj.subtract = 1;
obj.increment;
obj.decrement;
```