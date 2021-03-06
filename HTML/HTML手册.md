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
			* [font-size 属性](#font-size-属性)
			* [display 属性](#display-属性)
			* [position 属性](#position-属性)
		* [CSS](#css)
			* [:link :visited : hover : active](#link-visited-hover-active)
		* [HTML 元素](#html-元素)
			* [折行](#折行)
			* [URL 编码](#url-编码)
		* [CSS 框模型概述](#css-框模型概述)
			* [浏览器兼容性](#浏览器兼容性)
			* [术语翻译](#术语翻译)
			* [外边距](#外边距)
			* [CSS 外边距合并](#css-外边距合并)
		* [定位 (Positioning)](#定位-positioning)
	* [CSS 定位属性](#css-定位属性)
			* [相对定位](#相对定位)
			* [绝对定位](#绝对定位)
			* [浮动](#浮动)
			* [行框和清理](#行框和清理)
			* [clear 属性](#clear-属性)
	* [高级篇](#高级篇)
		* [box-sizing 属性](#box-sizing-属性)

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

#### display 属性

[官方参考](https://www.w3school.com.cn/cssref/pr_class_display.asp)

所有主流浏览器都支持 display 属性。

> 注释：如果规定了 !DOCTYPE，则 Internet Explorer 8 （以及更高版本）支持属性值 "inline-table"、"run-in"、"table"、"table-caption"、"table-cell"、"table-column"、"table-column-group"、"table-row"、"table-row-group"、以及 "inherit"。

**定义和用法**

display 属性规定元素应该生成的框的类型。

**说明**

这个属性用于定义建立布局时元素生成的显示框类型。对于 HTML 等文档类型，如果使用 display 不谨慎会很危险，因为可能违反 HTML 中已经定义的显示层次结构。对于 XML，由于 XML 没有内置的这种层次结构，所有 display 是绝对必要的。

> 注释：CSS2 中有值 compact 和 marker，不过由于缺乏广泛的支持，已经从 CSS2.1 中去除了。

**可能的值**

![display可能的值](https://raw.githubusercontent.com/Grekevin/development-manual-imgs/master/1610422767727.png)


#### position 属性

**定义和用法**

position 属性规定元素的定位类型。

**说明**

这个属性定义建立元素布局所用的定位机制。

> 任何元素都可以定位，不过绝对或固定元素会生成一个块级框，而不论该元素本身是什么类型。相对定位元素会相对于它在正常流中的默认位置偏移。

**可能的值**

![position取值](https://raw.githubusercontent.com/Grekevin/development-manual-imgs/master/1610423714372.png)

position 属性值的含义：

static
元素框正常生成。块级元素生成一个矩形框，作为文档流的一部分，行内元素则会创建一个或多个行框，置于其父元素中。

relative
元素框偏移某个距离。元素仍保持其未定位前的形状，它原本所占的空间仍保留。

absolute
元素框从文档流完全删除，并相对于其包含块定位。包含块可能是文档中的另一个元素或者是初始包含块。元素原先在正常文档流中所占的空间会关闭，就好像元素原来不存在一样。元素定位后生成一个块级框，而不论原来它在正常流中生成何种类型的框。

fixed
元素框的表现类似于将 position 设置为 absolute，不过其包含块是视窗本身。
提示：相对定位实际上被看作普通流定位模型的一部分，因为元素的位置相对于它在普通流中的位置。


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

#### 外边距

围绕在元素边框的空白区域是外边距。设置外边距会在元素外创建额外的“空白”。

设置外边距的最简单的方法就是使用 margin 属性，这个属性接受任何长度单位、百分数值甚至负值。

margin 属性接受任何长度单位，可以是像素、英寸、毫米或 em。

margin 可以设置为 auto。更常见的做法是为外边距设置长度值。

margin 的默认值是 0，所以如果没有为 margin 声明一个值，就不会出现外边距。但是，在实际中，浏览器对许多元素已经提供了预定的样式，外边距也不例外。例如，在支持 CSS 的浏览器中，外边距会在每个段落元素的上面和下面生成“空行”。因此，如果没有为 p 元素声明外边距，浏览器可能会自己应用一个外边距。当然，只要你特别作了声明，就会覆盖默认样式。

**提示和注释**

提示：Netscape 和 IE 对 body 标签定义的默认边距（margin）值是 8px。而 Opera 不是这样。相反地，Opera 将内部填充（padding）的默认值定义为 8px，因此如果希望对整个网站的边缘部分进行调整，并将之正确显示于 Opera 中，那么必须对 body 的 padding 进行自定义。

#### CSS 外边距合并

外边距合并指的是，当两个垂直外边距相遇时，它们将形成一个外边距。

合并后的外边距的高度等于两个发生合并的外边距的高度中的较大者。

> 注释：只有普通文档流中块框的垂直外边距才会发生外边距合并。行内框、浮动框或绝对定位之间的外边距不会合并。

### 定位 (Positioning)

**定位和浮动**

定位的基本思想很简单，它允许你定义元素框相对于其正常位置应该出现的位置，或者相对于父元素、另一个元素甚至浏览器窗口本身的位置。显然，这个功能非常强大，也很让人吃惊。要知道，用户代理对 CSS2 中定位的支持远胜于对其它方面的支持，对此不应感到奇怪。

另一方面，CSS1 中首次提出了浮动，它以 Netscape 在 Web 发展初期增加的一个功能为基础。浮动不完全是定位，不过，它当然也不是正常流布局。

**一切皆为框**

div、h1 或 p 元素常常被称为块级元素。这意味着这些元素显示为一块内容，即“块框”。

span 和 strong 等元素称为“行内元素”，这是因为它们的内容显示在行中，即“行内框”。

> 块框和行内框都可以通过style属性设置内边距、边框和外边距。

您可以使用 `display` 属性改变生成的框的类型。这意味着，通过将 `display` 属性设置为 `block`，可以让行内元素（比如 `<a>` 元素）表现得像块级元素一样。还可以通过把 `display` 设置为 `none`，让生成的元素根本没有框。这样的话，该框及其所有内容就不再显示，不占用文档中的空间。

但是在一种情况下，即使没有进行显式定义，也会创建块级元素。这种情况发生在把一些文本添加到一个块级元素（比如 `div`）的开头。即使没有把这些文本定义为段落，它也会被当作段落对待：

``` html
<div>
some text
<p>Some more text.</p>
</div>
```
在这种情况下，这个框称为无名块框，因为它不与专门定义的元素相关联。

块级元素的文本行也会发生类似的情况。假设有一个包含三行文本的段落。每行文本形成一个无名框。无法直接对无名块或行框应用样式，因为没有可以应用样式的地方（注意，行框和行内框是两个概念）。但是，这有助于理解在屏幕上看到的所有东西都形成某种框。

**CSS 定位机制**

CSS 有三种基本的定位机制：普通流、浮动和绝对定位。

除非专门指定，否则所有框都在普通流中定位。也就是说，普通流中的元素的位置由元素在 (X)HTML 中的位置决定。

块级框从上到下一个接一个地排列，框之间的垂直距离是由框的垂直外边距计算出来。

行内框在一行中水平布置。可以使用水平内边距、边框和外边距调整它们的间距。但是，垂直内边距、边框和外边距不影响行内框的高度。由一行形成的水平框称为行框（Line Box），行框的高度总是足以容纳它包含的所有行内框。不过，设置行高可以增加这个框的高度。

## CSS 定位属性

CSS 定位属性允许你对元素进行定位。

| 属性 | 描述 |
| --- | --- |
| [position](https://www.w3school.com.cn/cssref/pr_class_position.asp) | 把元素放置到一个静态的、相对的、绝对的、或固定的位置中。 |
| [top](https://www.w3school.com.cn/cssref/pr_pos_top.asp) | 定义了一个定位元素的上外边距边界与其包含块上边界之间的偏移。 |
| [right](https://www.w3school.com.cn/cssref/pr_pos_right.asp) | 定义了定位元素右外边距边界与其包含块右边界之间的偏移。 |
| [bottom](https://www.w3school.com.cn/cssref/pr_pos_bottom.asp) | 定义了定位元素下外边距边界与其包含块下边界之间的偏移。 |
| [left](https://www.w3school.com.cn/cssref/pr_pos_left.asp) | 定义了定位元素左外边距边界与其包含块左边界之间的偏移。 |
| [overflow](https://www.w3school.com.cn/cssref/pr_pos_overflow.asp) | 设置当元素的内容溢出其区域时发生的事情。 |
| [clip](https://www.w3school.com.cn/cssref/pr_pos_clip.asp) | 设置元素的形状。元素被剪入这个形状之中，然后显示出来。 |
| [vertical-align](https://www.w3school.com.cn/cssref/pr_pos_vertical-align.asp) | 设置元素的垂直对齐方式。 |
| [z-index](https://www.w3school.com.cn/cssref/pr_pos_z-index.asp) | 设置元素的堆叠顺序。 |

#### 相对定位

> 设置为相对定位的元素框会偏移某个距离。元素仍然保持其未定位前的形状，它原本所占的空间仍保留。

**CSS 相对定位**

相对定位是一个非常容易掌握的概念。如果对一个元素进行相对定位，它将出现在它所在的位置上。然后，可以通过设置垂直或水平位置，让这个元素“相对于”它的起点进行移动。

如果将 top 设置为 20px，那么框将在原位置顶部下面 20 像素的地方。如果 left 设置为 30 像素，那么会在元素左边创建 30 像素的空间，也就是将元素向右移动。

``` css
#box_relative {
  position: relative;
  left: 30px;
  top: 20px;
}
```
如下图所示：

![relative](https://raw.githubusercontent.com/Grekevin/development-manual-imgs/master/1610424916242.png)

> 注意，在使用相对定位时，无论是否进行移动，元素仍然占据原来的空间。因此，移动元素会导致它覆盖其它框。

#### 绝对定位

> 设置为绝对定位的元素框从文档流完全删除，并相对于其包含块定位，包含块可能是文档中的另一个元素或者是初始包含块。元素原先在正常文档流中所占的空间会关闭，就好像该元素原来不存在一样。元素定位后生成一个块级框，而不论原来它在正常流中生成何种类型的框。

绝对定位使元素的位置与文档流无关，因此不占据空间。这一点与相对定位不同，相对定位实际上被看作普通流定位模型的一部分，因为元素的位置相对于它在普通流中的位置。

普通流中其它元素的布局就像绝对定位的元素不存在一样：

``` css
#box_absolute {
  position: absolute;
  left: 30px;
  top: 20px;
}
```

如下图所示：

![absolute](https://raw.githubusercontent.com/Grekevin/development-manual-imgs/master/1610425064921.png)

绝对定位的元素的位置相对于_最近的已定位祖先元素_，如果元素没有已定位的祖先元素，那么它的位置相对于_最初的包含块_。

对于定位的主要问题是要记住每种定位的意义。所以，现在让我们复习一下学过的知识吧：相对定位是“相对于”元素在文档中的初始位置，而绝对定位是“相对于”最近的已定位祖先元素，如果不存在已定位的祖先元素，那么“相对于”最初的包含块。

注释：根据用户代理的不同，最初的包含块可能是画布或 HTML 元素。

提示：因为绝对定位的框与文档流无关，所以它们可以覆盖页面上的其它元素。可以通过设置 [z-index 属性](https://www.w3school.com.cn/cssref/pr_pos_z-index.asp "CSS z-index 属性")来控制这些框的堆放次序。

#### 浮动

> 浮动的框可以向左或向右移动，直到它的外边缘碰到包含框或另一个浮动框的边框为止。
由于浮动框不在文档的普通流中，所以文档的普通流中的块框表现得就像浮动框不存在一样。

请看下图，当把框 1 向右浮动时，它脱离文档流并且向右移动，直到它的右边缘碰到包含框的右边缘：

![enter description here](https://raw.githubusercontent.com/Grekevin/development-manual-imgs/master/1610425573858.png)

再请看下图，当框 1 向左浮动时，它脱离文档流并且向左移动，直到它的左边缘碰到包含框的左边缘。因为它不再处于文档流中，所以它不占据空间，实际上覆盖住了框 2，使框 2 从视图中消失。

如果把所有三个框都向左移动，那么框 1 向左浮动直到碰到包含框，另外两个框向左浮动直到碰到前一个浮动框。

![enter description here](https://raw.githubusercontent.com/Grekevin/development-manual-imgs/master/1610425639745.png)

如下图所示，如果包含框太窄，无法容纳水平排列的三个浮动元素，那么其它浮动块向下移动，直到有足够的空间。如果浮动元素的高度不同，那么当它们向下移动时可能被其它浮动元素“卡住”：

![enter description here](https://raw.githubusercontent.com/Grekevin/development-manual-imgs/master/1610425672691.png)


**可能的值**

| 值 | 描述 |
| --- | --- |
| left | 元素向左浮动。 |
| right | 元素向右浮动。 |
| none | 默认值。元素不浮动，并会显示在其在文本中出现的位置。 |
| inherit | 规定应该从父元素继承 float 属性的值。 |


#### 行框和清理

浮动框旁边的行框被缩短，从而给浮动框留出空间，行框围绕浮动框。

因此，创建浮动框可以使文本围绕图像：

![enter description here](https://raw.githubusercontent.com/Grekevin/development-manual-imgs/master/1610425787444.png)

要想阻止行框围绕浮动框，需要对该框应用 [clear 属性](https://www.w3school.com.cn/cssref/pr_class_clear.asp "CSS clear 属性")。clear 属性的值可以是 left、right、both 或 none，它表示框的哪些边不应该挨着浮动框。

为了实现这种效果，在被清理的元素的_上外边距_上添加足够的空间，使元素的顶边缘垂直下降到浮动框下面：

![enter description here](https://raw.githubusercontent.com/Grekevin/development-manual-imgs/master/1610425924904.png)

这是一个有用的工具，它让周围的元素为浮动元素留出空间。

让我们更详细地看看浮动和清理。假设希望让一个图片浮动到文本块的左边，并且希望这幅图片和文本包含在另一个具有背景颜色和边框的元素中。您可能编写下面的代码：

``` css
.news {
  background-color: gray;
  border: solid 1px black;
  }

.news img {
  float: left;
  }

.news p {
  float: right;
  }

<div class="news">
<img src="news-pic.jpg" />
<p>some text</p>
</div>
```

这种情况下，出现了一个问题。因为浮动元素脱离了文档流，所以包围图片和文本的 div 不占据空间。

如何让包围元素在视觉上包围浮动元素呢？需要在这个元素中的某个地方应用 clear：

![enter description here](https://raw.githubusercontent.com/Grekevin/development-manual-imgs/master/1610437571503.png)

不幸的是出现了一个新的问题，由于没有现有的元素可以应用清理，所以我们只能添加一个空元素并且清理它。

``` stylus
.news {
  background-color: gray;
  border: solid 1px black;
  }

.news img {
  float: left;
  }

.news p {
  float: right;
  }

.clear {
  clear: both;
  }

<div class="news">
<img src="news-pic.jpg" />
<p>some text</p>
`<div class="clear"></div>`
</div>
```

这样可以实现我们希望的效果，但是需要添加多余的代码。常常有元素可以应用 clear，但是有时候不得不为了进行布局而添加无意义的标记。

不过我们还有另一种办法，那就是对容器 div 进行浮动：

``` css
.news {
  background-color: gray;
  border: solid 1px black;
  `float: left;`
  }

.news img {
  float: left;
  }

.news p {
  float: right;
  }

<div class="news">
<img src="news-pic.jpg" />
<p>some text</p>
</div>
```

这样会得到我们希望的效果。不幸的是，下一个元素会受到这个浮动元素的影响。为了解决这个问题，有些人选择对布局中的所有东西进行浮动，然后使用适当的有意义的元素（常常是站点的页脚）对这些浮动进行清理。这有助于减少或消除不必要的标记。

事实上，W3School 站点上的所有页面都采用了这种技术，如果您打开我们使用 CSS 文件，您会看到我们对页脚的 div 进行了清理，而页脚上面的三个 div 都向左浮动。

#### clear 属性

**定义和用法**

clear 属性规定元素的哪一侧不允许其他浮动元素。

**说明**

clear 属性定义了元素的哪边上不允许出现浮动元素。在 CSS1 和 CSS2 中，这是通过自动为清除元素（即设置了 clear 属性的元素）增加上外边距实现的。在 CSS2.1 中，会在元素上外边距之上增加清除空间，而外边距本身并不改变。不论哪一种改变，最终结果都一样，如果声明为左边或右边清除，会使元素的上外边框边界刚好在该边上浮动元素的下外边距边界之下。

**可能的值**

| 值 | 描述 |
| --- | --- |
| left | 在左侧不允许浮动元素。 |
| right | 在右侧不允许浮动元素。 |
| both | 在左右两侧均不允许浮动元素。 |
| none | 默认值。允许浮动元素出现在两侧。 |
| inherit | 规定应该从父元素继承 clear 属性的值。 |



## 高级篇

### box-sizing 属性

[官方文档](https://developer.mozilla.org/zh-CN/docs/Web/CSS/box-sizing)

CSS 中的 **`box-sizing` **属性定义了 [user agent](https://developer.mozilla.org/zh-CN/docs/Glossary/User_agent) 应该如何计算一个元素的总宽度和总高度。

在 [CSS 盒子模型](https://developer.mozilla.org/en-US/docs/CSS/Box_model "CSS/Box_model")的默认定义里，你对一个元素所设置的 [`width`](https://developer.mozilla.org/zh-CN/docs/Web/CSS/width "width 属性用于设置元素的宽度。width 默认设置内容区域的宽度，但如果 box-sizing 属性被设置为 border-box，就转而设置边框区域的宽度。") 与 [`height`](https://developer.mozilla.org/zh-CN/docs/Web/CSS/height) 只会应用到这个元素的内容区。如果这个元素有任何的 [`border`](https://developer.mozilla.org/zh-CN/docs/Web/CSS/border "CSS的border属性是一个用于设置各种单独的边界属性的简写属性。border可以用于设置一个或多个以下属性的值： border-width, border-style, border-color。") 或 [`padding`](https://developer.mozilla.org/zh-CN/docs/Web/CSS/padding "padding CSS 简写属性控制元素所有四条边的内边距区域。") ，绘制到屏幕上时的盒子宽度和高度会加上设置的边框和内边距值。这意味着当你调整一个元素的宽度和高度时需要时刻注意到这个元素的边框和内边距。当我们实现响应式布局时，这个特点尤其烦人。

box-sizing 属性可以被用来调整这些表现:

*   `content-box`  是默认值。如果你设置一个元素的宽为100px，那么这个元素的内容区会有100px 宽，并且任何边框和内边距的宽度都会被增加到最后绘制出来的元素宽度中。
*   `border-box` 告诉浏览器：你想要设置的边框和内边距的值是包含在width内的。也就是说，如果你将一个元素的width设为100px，那么这100px会包含它的border和padding，内容区的实际宽度是width减去(border + padding)的值。大多数情况下，这使得我们更容易地设定一个元素的宽高。

**译者注:** `border-box`不包含`margin`

Note: 对于新的web站点，你可能希望首先将box-sizing设置为border-box，如下所示：


``` css
* { box-sizing: border-box; }
```

这使得处理元素大小的工作变得容易得多，并且通常消除了在布局内容时可能遇到的许多陷阱。然而，在某些情况下，你应谨慎使用这个属性。例如： 你正在编写一个将由其他人使用的共享组件库，如果他们网站的其余部分没有设置此值，他们可能会发现很难使用你的组件库。


###  id和class区分大小写
请注意，类选择器和 ID 选择器可能是区分大小写的。这取决于文档的语言。HTML 和 XHTML 将类和 ID 值定义为区分大小写，所以类和 ID 值的大小写必须与文档中的相应值匹配。


### 使用 margin 属性来水平对齐

可通过将左和右外边距设置为 "auto"，来对齐块元素。

> 注释：除非已经声明了 !DOCTYPE，否则使用 margin:auto 在 IE8 以及更早的版本中是无效的。

把左和右外边距设置为 auto，规定的是均等地分配可用的外边距。结果就是居中的元素。

``` css
.center
{
margin-left:auto;
margin-right:auto;
width:70%;
background-color:#b0e0e6;
}
```

> 提示：如果宽度是 100%，则对齐没有效果。

### 使用 position 属性进行左和右对齐

对齐元素的方法之一是使用绝对定位：

``` css
right
{
position:absolute;
right:0px;
width:300px;
background-color:#b0e0e6;
}
```

> 注释：绝对定位元素会被从正常流中删除，并且能够交叠元素。

**跨浏览器兼容性问题**

当像这样对齐元素时，对 `<body>` 元素的外边距和内边距进行预定义是一个好主意。这样可以避免在不同的浏览器中出现可见的差异。

当使用 position 属性时，IE8 以及更早的版本存在一个问题。如果容器元素（在我们的案例中是 `<div class="container">`）设置了指定的宽度，并且省略了 !DOCTYPE 声明，那么 IE8 以及更早的版本会在右侧增加 17px 的外边距。这似乎是为滚动条预留的空间。当使用 position 属性时，请始终设置 !DOCTYPE 声明：

``` css
body
{
margin:0;
padding:0;
}
.container
{
position:relative;
width:100%;
}
.right
{
position:absolute;
right:0px;
width:300px;
background-color:#b0e0e6;
}
```

### 使用 float 属性来进行左和右对齐

对齐元素的另一种方法是使用 float 属性：

``` css
.right
{
float:right;
width:300px;
background-color:#b0e0e6;
}
```

**跨浏览器兼容性问题**

当像这样对齐元素时，对 `<body>` 元素的外边距和内边距进行预定义是一个好主意。这样可以避免在不同的浏览器中出现可见的差异。

当使用 float 属性时，IE8 以及更早的版本存在一个问题。如果省略 !DOCTYPE 声明，那么 IE8 以及更早的版本会在右侧增加 17px 的外边距。这似乎是为滚动条预留的空间。当使用 float 属性时，请始终设置 !DOCTYPE 声明：

``` css
body
{
margin:0;
padding:0;
}

.right
{
float:right;
width:300px;
background-color:#b0e0e6;
}
```