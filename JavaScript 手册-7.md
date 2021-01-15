

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

