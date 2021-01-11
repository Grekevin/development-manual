* [HTML手册](#html手册)
	* [属性](#属性)
		* [规范](#规范)
		* [background 属性](#background-属性)
			* [background-image 属性](#background-image-属性)
			* [background-position 属性](#background-position-属性)
			* [background-color 属性](#background-color-属性)
			* [background-image 属性](#background-image-属性)
		* [color 属性](#color-属性)
			* [style 属性](#style-属性)
			* [font 属性](#font-属性)
			* [Form 属性](#form-属性)
		* [CSS](#css)
			* [:link :visited : hover : active](#link-visited-hover-active)
		* [HTML 元素](#html-元素)
			* [折行](#折行)
			* [URL 编码](#url-编码)

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

**不要忘记结束标签**

即使忘了使用结束标签，大多数浏览器也会正确地将 HTML 显示出来。

通过结束标签来关闭 HTML 是一种经得起未来考验的 HTML 编写方法。清楚地标记某个元素在何处开始，并在何处结束，不论对您还是对浏览器来说，都会使代码更容易理解。

``` html
<p>This is a paragraph
<p>This is another paragraph
```
上面的例子在大多数浏览器中都没问题，但不要依赖这种做法。忘记使用结束标签会产生意想不到的结果和错误。

> 注释：在未来的 HTML 版本中，不允许省略结束标签。

**HTML 输出 - 有用的提示**

我们无法确定 HTML 被显示的确切效果。屏幕的大小，以及对窗口的调整都可能导致不同的结果。

对于 HTML，您无法通过在 HTML 代码中添加额外的空格或换行来改变输出的效果。

> 当显示页面时，浏览器会移除源代码中多余的空格和空行。所有连续的空格或空行都会被算作一个空格。需要注意的是，HTML 代码中的所有连续的空行（换行）也被显示为一个空格。


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

background-position 的默认值是 0% 0%，在功能上相当于 top left。这就解释了背景图像为什么总是从元素内边距区的左上角开始平铺，除非您设置了不同的位置值。

> 提示：您需要把 background-attachment 属性设置为 "fixed"，才能保证该属性在 Firefox 和 Opera 中正常工作。

**关键字**

``` css
p
  { 
    background-image:url('bgimg.gif');
    background-repeat:no-repeat;
    background-position:top;
  }
```

为 background-position 属性提供值有很多方法。首先，可以使用一些关键字：top、bottom、left、right 和 center。通常，这些关键字会成对出现，不过也不总是这样。还可以使用长度值，如 100px 或 5cm，最后也可以使用百分数值。不同类型的值对于背景图像的放置稍有差异。

图像放置关键字最容易理解，其作用如其名称所表明的。例如，top right 使图像放置在元素内边距区的右上角。

根据规范，位置关键字可以按任何顺序出现，只要保证不超过两个关键字 - 一个对应水平方向，另一个对应垂直方向。

如果只出现一个关键字，则认为另一个关键字是 center。

**百分数值**

百分数值的表现方式更为复杂。假设你希望用百分数值将图像在其元素中居中，这很容易：

``` css
body
  { 
    background-image:url('/i/eg_bg_03.gif');
    background-repeat:no-repeat;
    background-position:50% 50%;
  }
```
这会导致图像适当放置，其中心与其元素的中心对齐。换句话说，百分数值同时应用于元素和图像。也就是说，图像中描述为 50% 50% 的点（中心点）与元素中描述为 50% 50% 的点（中心点）对齐。

如果图像位于 0% 0%，其左上角将放在元素内边距区的左上角。如果图像位置是 100% 100%，会使图像的右下角放在右边距的右下角。

因此，如果你想把一个图像放在水平方向 2/3、垂直方向 1/3 处，可以这样声明：

``` css
body
  { 
    background-image:url('/i/eg_bg_03.gif');
    background-repeat:no-repeat;
    background-position:66% 33%;
  }
```
如果只提供一个百分数值，所提供的这个值将用作水平值，垂直值将假设为 50%。这一点与关键字类似。

**长度值**

长度值解释的是元素内边距区左上角的偏移。偏移点是图像的左上角。

比如，如果设置值为 50px 100px，图像的左上角将在元素内边距区左上角向右 50 像素、向下 100 像素的位置上：

``` css
body
  { 
    background-image:url('/i/eg_bg_03.gif');
    background-repeat:no-repeat;
    background-position:50px 100px;
  }
```

> 注意，这一点与百分数值不同，因为偏移只是从一个左上角到另一个左上角。也就是说，图像的左上角与 background-position 声明中的指定的点对齐。

#### background-color 属性

**定义和用法**

background-color 属性设置元素的背景颜色。

**元素背景的范围**

background-color 属性为元素设置一种纯色。这种颜色会填充元素的内容、内边距和边框区域，扩展到元素边框的外边界（但不包括外边距）。如果边框有透明部分（如虚线边框），会透过这些透明部分显示出背景色。

**transparent 值**

尽管在大多数情况下，没有必要使用 transparent。不过如果您不希望某元素拥有背景色，同时又不希望用户对浏览器的颜色设置影响到您的设计，那么设置 transparent 值还是有必要的。

> background-color 不能继承，其默认值是 transparent。transparent 有“透明”之意。也就是说，如果一个元素没有指定背景色，那么背景就是透明的，这样其祖先元素的背景才能可见。

#### background-image 属性

background-image 也不能继承。事实上，所有背景属性都不能继承。

### color 属性

**定义和用法**

 - color 属性规定文本的颜色。
 - 这个属性设置了一个元素的前景色（在 HTML 表现中，就是元素文本的颜色）；光栅图像不受 color 影响。这个颜色还会应用到元素的所有边框，除非被 border-color 或另外某个边框颜色属性覆盖。
 - 要设置一个元素的前景色，最容易的方法是使用 color 属性。

**提示和注释**

> 提示：请使用合理的背景颜色和文本颜色搭配，这样可以提高文本的可读性。

#### style 属性

**style 属性的作用：**

提供了一种改变所有 HTML 元素的样式的通用方法。

样式是 HTML 4 引入的，它是一种新的首选的改变 HTML 元素样式的方式。通过 HTML 样式，能够通过使用 style 属性直接将样式添加到 HTML 元素，或者间接地在独立的样式表中（CSS 文件）进行定义。

#### font 属性

font-family、color 以及 font-size 属性分别定义元素中文本的字体系列、颜色和字体尺寸：

``` html
<html>

<body>
<h1 style="font-family:verdana">A heading</h1>
<p style="font-family:arial;color:red;font-size:20px;">A paragraph.</p>
</body>

</html>
```

#### Form 属性

HTML `<form>` 元素，已设置所有可能的属性，是这样的：

实例：

``` html
<form action="action_page.php" method="GET" target="_blank" accept-charset="UTF-8"
ectype="application/x-www-form-urlencoded" autocomplete="off" novalidate>
.
form elements
 .
</form> 
```
下面是 `<form>` 属性的列表：

![form 属性](https://raw.githubusercontent.com/Grekevin/development-manual-imgs/master/1610349843904.png)

#### font-size 属性

font-size 属性设置文本的大小。

font-size 值可以是绝对或相对值。

绝对值：

 - 将文本设置为指定的大小
 - 不允许用户在所有浏览器中改变文本大小（不利于可用性）
 - 绝对大小在确定了输出的物理尺寸时很有用

相对大小：

 - 相对于周围的元素来设置大小
 - 允许用户在浏览器改变文本大小

> 注意：如果您没有规定字体大小，普通文本（比如段落）的默认大小是 16 像素 (16px=1em)。

**使用像素来设置字体大小**

通过像素设置文本大小，可以对文本大小进行完全控制：

``` css
h1 {font-size:60px;}
h2 {font-size:40px;}
p {font-size:14px;}
```

**使用 em 来设置字体大小**

如果要避免在 Internet Explorer 中无法调整文本的问题，许多开发者使用 em 单位代替 pixels。

> W3C 推荐使用 em 尺寸单位。

1em 等于当前的字体尺寸。如果一个元素的 font-size 为 16 像素，那么对于该元素，1em 就等于 16 像素。在设置字体大小时，em 的值会相对于父元素的字体大小改变。

> 浏览器中默认的文本大小是 16 像素。因此 1em 的默认尺寸是 16 像素。

可以使用下面这个公式将像素转换为 em：pixels/16=em

> （注：16 等于父元素的默认字体大小，假设父元素的 font-size 为 20px，那么公式需改为：pixels/20=em）

``` css
h1 {font-size:3.75em;} /* 60px/16=3.75em */
h2 {font-size:2.5em;}  /* 40px/16=2.5em */
p {font-size:0.875em;} /* 14px/16=0.875em */
```

在上面的例子中，以 em 为单位的文本大小与前一个例子中以像素计的文本是相同的。不过，如果使用 em 单位，则可以在所有浏览器中调整文本大小。

不幸的是，在 IE 中仍存在问题。在重设文本大小时，会比正常的尺寸更大或更小。

**结合使用百分比和 EM**

在所有浏览器中均有效的方案是为 body 元素（父元素）以百分比设置默认的 font-size 值：

``` css
body {font-size:100%;}
h1 {font-size:3.75em;}
h2 {font-size:2.5em;}
p {font-size:0.875em;}
```

我们的代码非常有效。在所有浏览器中，可以显示相同的文本大小，并允许所有浏览器缩放文本的大小。



### CSS

#### :link :visited : hover : active

链接的特殊性在于能够根据它们所处的状态来设置它们的样式。

链接的四种状态：

 - a:link - 普通的、未被访问的链接
 - a:visited - 用户已访问的链接
 - a:hover - 鼠标指针位于链接的上方
 - a:active - 链接被点击的时刻

``` css
a:link {color: #FF0000}     /* 未访问的链接 */
a:visited {color: #00FF00}  /* 已访问的链接 */
a:hover {color: #FF00FF}    /* 当有鼠标悬停在链接上 */
a:active {color: #0000FF}   /* 被选择的链接 */
```

> 注释：为了产生预期的效果，在 CSS 定义中，a:hover 必须位于 a:link 和 a:visited 之后！！

> 注释：为了产生预期的效果，在 CSS 定义中，a:active 必须位于 a:hover 之后！！

> 注释：Pseudo-class（伪类）的名称对大小写不敏感。

当为链接的不同状态设置样式时，请按照以下次序规则：

 - a:hover 必须位于 a:link 和 a:visited 之后
 - a:active 必须位于 a:hover 之后

**伪类可与 CSS 类配合使用：**

``` html
a.red:visited {color: #FF0000;}

<a class="red" href="css_syntax.asp">CSS Syntax</a>
```

### HTML 元素

#### 折行

如果您希望在不产生一个新段落的情况下进行换行（新行），请使用 <br /> 标签：

``` html
<p>This is<br />a para<br />graph with line breaks</p>
```

#### URL 编码

 - URL 只能使用 ASCII 字符集来通过因特网进行发送。
 - 由于 URL 常常会包含 ASCII 集合之外的字符，URL 必须转换为有效的 ASCII 格式。
 - URL 编码使用 "%" 其后跟随两位的十六进制数来替换非 ASCII 字符。
 - URL 不能包含空格。URL 编码通常使用 + 来替换空格。


### CSS 框模型概述

![CSS盒模型](https://raw.githubusercontent.com/Grekevin/development-manual-imgs/master/1610375755239.png)

元素框的最内部分是实际的内容，直接包围内容的是内边距。内边距呈现了元素的背景。内边距的边缘是边框。边框以外是外边距，外边距默认是透明的，因此不会遮挡其后的任何元素。

提示：背景应用于由内容和内边距、边框组成的区域。

内边距、边框和外边距都是可选的，默认值是零。但是，许多元素将由用户代理样式表设置外边距和内边距。可以通过将元素的 margin 和 padding 设置为零来覆盖这些浏览器样式。这可以分别进行，也可以使用通用选择器对所有元素进行设置：

``` css
* {
  margin: 0;
  padding: 0;
}
```

在 CSS 中，width 和 height 指的是内容区域的宽度和高度。增加内边距、边框和外边距不会影响内容区域的尺寸，但是会增加元素框的总尺寸。

假设框的每个边上有 10 个像素的外边距和 5 个像素的内边距。如果希望这个元素框达到 100 个像素，就需要将内容的宽度设置为 70 像素，请看下图：

![CSS 框模型实例](https://raw.githubusercontent.com/Grekevin/development-manual-imgs/master/1610375806826.png)

``` css
#box {
  width: 70px;
  margin: 10px;
  padding: 5px;
}
```

提示：内边距、边框和外边距可以应用于一个元素的所有边，也可以应用于单独的边。

提示：外边距可以是负值，而且在很多情况下都要使用负值的外边距。

#### 浏览器兼容性

一旦为页面设置了恰当的 DTD，大多数浏览器都会按照上面的图示来呈现内容。然而 IE 5 和 6 的呈现却是不正确的。根据 W3C 的规范，元素内容占据的空间是由 width 属性设置的，而内容周围的 padding 和 border 值是另外计算的。不幸的是，IE5.X 和 6 在怪异模式中使用自己的非标准模型。这些浏览器的 width 属性不是内容的宽度，而是内容、内边距和边框的宽度的总和。

虽然有方法解决这个问题。但是目前最好的解决方案是回避这个问题。也就是，不要给元素添加具有指定宽度的内边距，而是尝试将内边距或外边距添加到元素的父元素和子元素。

#### 术语翻译

*   element : 元素。
*   padding : 内边距，也有资料将其翻译为填充。
*   border : 边框。
*   margin : 外边距，也有资料将其翻译为空白或空白边。

在 w3school，我们把 padding 和 margin 统一地称为内边距和外边距。边框内的空白是内边距，边框外的空白是外边距。

**内边距的百分比数值**

前面提到过，可以为元素的内边距设置百分数值。百分数值是相对于其父元素的 width 计算的，这一点与外边距一样。所以，如果父元素的 width 改变，它们也会改变。

> 注意：上下内边距与左右内边距一致；即上下内边距的百分数会相对于父元素宽度设置，而不是相对于高度。

**边框与背景**

CSS 规范指出，边框绘制在“元素的背景之上”。这很重要，因为有些边框是“间断的”（例如，点线边框或虚线框），元素的背景应当出现在边框的可见部分之间。

CSS2 指出背景只延伸到内边距，而不是边框。后来 CSS2.1 进行了更正：元素的背景是内容、内边距和边框区的背景。大多数浏览器都遵循 CSS2.1 定义，不过一些较老的浏览器可能会有不同的表现。

**没有边框**

在前面的例子中，您已经看到，如果希望显示某种边框，就必须设置边框样式，比如 solid 或 outset。

那么如果把 border-style 设置为 none 会出现什么情况：

``` css
p {border-style: none; border-width: 50px;}
```

尽管边框的宽度是 50px，但是边框样式设置为 none。在这种情况下，不仅边框的样式没有了，其宽度也会变成 0。边框消失了，为什么呢？

这是因为如果边框样式为 none，即边框根本不存在，那么边框就不可能有宽度，因此边框宽度自动设置为 0，而不论您原先定义的是什么。

记住这一点非常重要。事实上，忘记声明边框样式是一个常犯的错误。根据以下规则，所有 h1 元素都不会有任何边框，更不用说 20 像素宽了：

``` css
h1 {border-width: 20px;}
```

由于 border-style 的默认值是 none，如果没有声明样式，就相当于 border-style: none。

> 因此，如果您希望边框出现，就必须声明一个边框样式。

**边框颜色**

默认的边框颜色是元素本身的前景色。如果没有为边框声明颜色，它将与元素的文本颜色相同。另一方面，如果元素没有任何文本，假设它是一个表格，其中只包含图像，那么该表的边框颜色就是其父元素的文本颜色（因为 color 可以继承）。这个父元素很可能是 body、div 或另一个 table。

**透明边框**

如果边框没有样式，就没有宽度。不过有些情况下您可能希望创建一个不可见的边框。

CSS2 引入了边框颜色值 transparent。这个值用于创建有宽度的不可见边框。请看下面的例子：

``` html
<a href="#">AAA</a>
<a href="#">BBB</a>
<a href="#">CCC</a>
```

我们为上面的链接定义了如下样式：

``` css
a:link, a:visited {
  border-style: solid;
  border-width: 5px;
  `border-color: transparent;`
  }
a:hover {border-color: gray;}
```

从某种意义上说，利用 transparent，使用边框就像是额外的内边距一样；此外还有一个好处，就是能在你需要的时候使其可见。这种透明边框相当于内边距，因为元素的背景会延伸到边框区域（如果有可见背景的话）。

> 重要事项：在 IE7 之前，IE/WIN 没有提供对 transparent 的支持。在以前的版本，IE 会根据元素的 color 值来设置边框颜色。

