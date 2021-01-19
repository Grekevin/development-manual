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

### 窗口尺寸

两个属性可用用于确定浏览器窗口的尺寸。

这两个属性都以像素返回尺寸：

``` javascript
window.innerHeight - 浏览器窗口的内高度（以像素计）
window.innerWidth - 浏览器窗口的内宽度（以像素计）
```

浏览器窗口（浏览器视口）不包括工具栏和滚动条。

对于 Internet Explorer 8, 7, 6, 5：

``` javascript
document.documentElement.clientHeight
document.documentElement.clientWidth
//或
document.body.clientHeight
document.body.clientWidth
```

一个实用的 JavaScript 解决方案（包括所有浏览器）：

``` javascript
var w = window.innerWidth
|| document.documentElement.clientWidth
|| document.body.clientWidth;

var h = window.innerHeight
|| document.documentElement.clientHeight
|| document.body.clientHeight; 
```

### 其他窗口方法

一些其他方法：

 - window.open() - 打开新窗口
 - window.close() - 关闭当前窗口
 - window.moveTo() -移动当前窗口
 - window.resizeTo() -重新调整当前窗口

## JavaScript Window Screen

> window.screen 对象包含用户屏幕的信息。

### Window Screen

window.screen 对象不带 window 前缀也可以写：

属性：

 - screen.width (返回以像素计的访问者屏幕宽度)
 - screen.height (返回以像素计的访问者屏幕的高度)
 - screen.availWidth (返回访问者屏幕的宽度，以像素计，减去诸如窗口工具条之类的界面特征)
 - screen.availHeight (返回访问者屏幕的高度，以像素计，减去诸如窗口工具条之类的界面特征)
 - screen.colorDepth 
 - screen.pixelDepth (返回屏幕的像素深度,对于现代计算机，颜色深度和像素深度是相等的。)

### Window Screen 色深

screen.colorDepth 属性返回用于显示一种颜色的比特数。

所有现代计算机都使用 24 位或 32 位硬件的色彩分辨率：

 - 24 bits =16,777,216 种不同的 "True Colors"
 - 32 bits = 4,294,967,296 中不同的 "Deep Colors"

更老的计算机使用 14 位：65,536 种不同的 "High Colors" 分辨率。

异常古老的计算机，以及老式的手机使用 8 位：256 中不同的 "VGA colors"。

显示以位计的屏幕色彩深度：

``` javascript
document.getElementById("demo").innerHTML = "Screen Color Depth: " + screen.colorDepth;
```

结果将是：

``` javascript
Screen Color Depth: 24
```

> HTML 中使用的 #rrggbb (rgb) 值代表 "True Colors" （16,777,216 中不同的颜色）。

