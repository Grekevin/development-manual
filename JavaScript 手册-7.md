

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

**属性 Getter 和 Setter**

ES5 允许您使用类似于获取或设置属性的语法来定义对象方法。

这个例子为名为 fullName 的属性创建一个 getter：

``` javascript
// 创建对象：
var person = {
  firstName: "Bill",
  lastName : "Gates",
  get fullName() {
    return this.firstName + " " + this.lastName;
  }
};

// 使用 getter 显示来自对象的数据：
document.getElementById("demo").innerHTML = person.fullName;
```

这个例子为语言属性创建一个 setter 和一个 getter：

``` javascript
var person = {
  firstName: "Bill",
  lastName : "Gates",
  language : "NO",
  get lang() {
    return this.language;
  },
  set lang(value) {
    this.language = value;
  }
};

// 使用 setter 设置对象属性：
person.lang = "en";

// 使用 getter 显示来自对象的数据：
document.getElementById("demo").innerHTML = person.lang;
```

