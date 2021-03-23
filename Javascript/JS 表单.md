* [JS 表单](#js-表单)
	* [JavaScript 表单验证](#javascript-表单验证)
	* [自动 HTML 表单验证](#自动-html-表单验证)
	* [数据验证](#数据验证)
	* [HTML 约束验证](#html-约束验证)
	* [JavaScript 验证 API](#javascript-验证-api)
		* [约束验证 DOM 方法](#约束验证-dom-方法)
		* [约束验证 DOM 属性](#约束验证-dom-属性)
		* [合法性属性](#合法性属性)

# JS 表单

## JavaScript 表单验证

HTML 表单验证能够通过 JavaScript 来完成。

如果某个表单字段是空的，那么该函数会发出一条警告消息，并返回 false，以防止表单被提交出去：

JavaScript 实例

``` javascript
function validateForm() {
    var x = document.forms["myForm"]["fname"].value;
    if (x == "") {
        alert("必须填写姓名");
        return false;
    }
}
```

该函数能够在表单提交时被调用：

HTML 表单实例

``` HTML 
<form name="myForm" action="/action_page_post.php" onsubmit="return validateForm()" method="post">
姓名：<input type="text" name="fname">
<input type="submit" value="Submit">
</form>
```

## 自动 HTML 表单验证
HTML 表单验证能够被浏览器自动执行：

如果表单字段（fname）是空的，required 属性防止表单被提交：

HTML 表单实例

``` html 
<form action="/action_page_post.php" method="post">
   <input type="text" name="fname" required>
   <input type="submit" value="Submit">
</form>
```

自动 HTML 表单验证不适用于 Internet Explorer 9 或更早的版本。

## 数据验证

数据验证指的是确保干净、正确和有用的用户输入的过程。

典型的验证任务是：

 - 用户是否已填写所有必需的字段？
 - 用户是否已输入有效的日期？
 - 用户是否在数字字段中输入了文本？

大多数情况下，数据验证的作用是确保正确的用户输入。

验证可以通过很多不同的方法来定义，并且可以使用很多不同的方法来开发。

服务器端验证是由 web 服务器执行的，在输入被送往服务器之后。

客户端验证是由 web 浏览器执行的，在输入被送往 web 服务器之前。

## HTML 约束验证

HTML5 引入了一种新的 HTML 验证概念，名为约束验证（constraint validation）。

HTML 约束验证基于：

 - 约束验证 HTML 输入属性
 - 约束验证 CSS 伪选择器
 - 约束验证 DOM 属性和方法

[详细参考文档](https://www.w3school.com.cn/js/js_validation.asp)

## JavaScript 验证 API

### 约束验证 DOM 方法

| 属性 | 描述 |
| --- | --- |
| checkValidity() | 返回 true，如果 input 元素包含有效数据 |
| setCustomValidity() | 设置 input 元素的 validationMessage 属性。 |

**checkValidity() 方法**

如果输入字段包含无效的数据，显示一条消息：

``` html
<input id="id1" type="number" min="100" max="300" required>
<button onclick="myFunction()">OK</button>

<p id="demo"></p>

<script>
 function myFunction() {
    var inpObj = document.getElementById("id1");
    if (inpObj.checkValidity() == false) {
        document.getElementById("demo").innerHTML = inpObj.validationMessage;
    }
}
</script>
```

###  约束验证 DOM 属性

| 属性 | 描述 |
| --- | --- |
| validity | 包含与 input 元素的合法性相关的布尔属性。 |
| validationMessage | 包含当 validity 为 false 时浏览器显示的消息。 |
| willValidate | 指示是否验证 input 元素。 |

### 合法性属性

input 元素的 validity 属性包含了与数据合法性相关的一系列属性：

| 属性 | 描述 |
| --- | --- |
| customError | 设置为 true，如果设置自定义的合法性消息。 |
| patternMismatch | 设置为 true，如果元素值不匹配其 pattern 属性。 |
| rangeOverflow | 设置为 true，如果元素值大于其 max 属性。 |
| rangeUnderflow | 设置为 true，如果元素值小于其 min 属性。 |
| stepMismatch | 当字段拥有 step 属性，且输入的 value 值不符合设定的间隔值时，该属性值为 true。 |
| tooLong | 设置为 true，如果元素值超过了其 maxLength 属性。 |
| typeMismatch | 当字段的 type 是 email 或者 url 但输入的值不是正确的类型时，属性值为 true。 |
| valueMissing | 设置为 true，如果元素（包含 required）没有值。 |
| valid | 设置为 true，如果元素值是有效的。 |

**实例**

如果输入字段中的数字大于 100（input 元素的 max 属性），则显示一条消息：

rangeOverflow 属性

``` html
<input id="id1" type="number" max="100">
<button onclick="myFunction()">OK</button>

<p id="demo"></p>

<script>
function myFunction() {
    var txt = "";
    if (document.getElementById("id1").validity.rangeOverflow) {
        txt = "值太大";
    }
     document.getElementById("demo").innerHTML = txt;
}
</script> 
```

如果输入字段中的数字小于 100（input 元素的 min 属性），则显示一条消息：

rangeUnderflow 属性

``` html
<input id="id1" type="number" min="100">
<button onclick="myFunction()">OK</button>

<p id="demo"></p>

<script>
function myFunction() {
     var txt = "";
    if (document.getElementById("id1").validity.rangeUnderflow) {
        txt = "值太小";
    }
     document.getElementById("demo").innerHTML = txt;
}
</script>
```