* [HTML手册](#html手册)
	* [属性](#属性)
		* [background 属性](#background-属性)
			* [background-image 属性](#background-image-属性)

# HTML手册

## 属性

### 规范

**HTML 提示：使用小写属性**

属性和属性值对大小写不敏感。

不过，万维网联盟在其 HTML 4 推荐标准中推荐小写的属性/属性值。

而新版本的 (X)HTML 要求使用小写属性。

**始终为属性值加引号**

属性值应该始终被包括在引号内。双引号是最常用的，不过使用单引号也没有问题。

在某些个别的情况下，比如属性值本身就含有双引号，那么您必须使用单引号，例如：

``` HTML
name='Bill "HelloWorld" Gates'
```

### background 属性

#### background-image 属性

**定义和用法**

 - background-image 属性为元素设置背景图像。
 - 元素的背景占据了元素的全部尺寸，包括内边距和边框，但不包括外边距。
 - 默认地，背景图像位于元素的左上角，并在水平和垂直方向上重复。
 - 提示：请设置一种可用的背景颜色，这样的话，假如背景图像不可用，页面也可获得良好的视觉效果。
 - 根据 background-repeat 属性的值，图像可以无限平铺、沿着某个轴（x 轴或 y 轴）平铺，或者根本不平铺。
 - 初始背景图像（原图像）根据 background-position 属性的值放置。

> 提示：背景图像的位置是根据 background-position 属性设置的。如果未规定 background-position 属性，图像会被放置在元素的左上角。
> 
> background-repeat 属性设置是否及如何重复背景图像。默认地，背景图像在水平和垂直方向上重复。

#### background-position 属性

background-position 属性设置背景图像（由 background-image 定义）的起始位置。

> 提示：您需要把 background-attachment 属性设置为 "fixed"，才能保证该属性在 Firefox 和 Opera 中正常工作。

#### background-color 属性

**定义和用法**

background-color 属性设置元素的背景颜色。

**元素背景的范围**

background-color 属性为元素设置一种纯色。这种颜色会填充元素的内容、内边距和边框区域，扩展到元素边框的外边界（但不包括外边距）。如果边框有透明部分（如虚线边框），会透过这些透明部分显示出背景色。

**transparent 值**

尽管在大多数情况下，没有必要使用 transparent。不过如果您不希望某元素拥有背景色，同时又不希望用户对浏览器的颜色设置影响到您的设计，那么设置 transparent 值还是有必要的。

### color 属性

**定义和用法**

 - color 属性规定文本的颜色。
 - 这个属性设置了一个元素的前景色（在 HTML 表现中，就是元素文本的颜色）；光栅图像不受 color 影响。这个颜色还会应用到元素的所有边框，除非被 border-color 或另外某个边框颜色属性覆盖。
 - 要设置一个元素的前景色，最容易的方法是使用 color 属性。

**提示和注释**

> 提示：请使用合理的背景颜色和文本颜色搭配，这样可以提高文本的可读性。

### CSS 伪类

#### :link :visited : hover : active

``` css
a:link {color: #FF0000}     /* 未访问的链接 */
a:visited {color: #00FF00}  /* 已访问的链接 */
a:hover {color: #FF00FF}    /* 当有鼠标悬停在链接上 */
a:active {color: #0000FF}   /* 被选择的链接 */
```

> 注释：为了产生预期的效果，在 CSS 定义中，a:hover 必须位于 a:link 和 a:visited 之后！！

> 注释：为了产生预期的效果，在 CSS 定义中，a:active 必须位于 a:hover 之后！！

> 注释：Pseudo-class（伪类）的名称对大小写不敏感。

**伪类可与 CSS 类配合使用：**

``` html
a.red:visited {color: #FF0000;}

<a class="red" href="css_syntax.asp">CSS Syntax</a>
```

