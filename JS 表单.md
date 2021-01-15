

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

