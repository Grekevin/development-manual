#  JS Browser BOM
## JavaScript Window - 浏览器对象模型

> 浏览器对象模型（Browser Object Model (BOM)）允许 JavaScript 与浏览器对话。

### 浏览器对象模型（Browser Object Model (BOM)）

不存在浏览器对象模型（BOM）的官方标准。

现代的浏览器已经（几乎）实现了 JavaScript 交互相同的方法和属性，因此它经常作为 BOM 的方法和属性被提到。

### Window 对象

所有浏览器都支持 window 对象。它代表浏览器的窗口。

所有全局 JavaScript 对象，函数和变量自动成为 window 对象的成员。

全局变量是 window 对象的属性。

全局函数是 window 对象的方法。

甚至（HTML DOM 的）document 对象也是 window 对象属性：

``` javascript
window.document.getElementById("header");
//等同于：
document.getElementById("header");
```

