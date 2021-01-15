

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

