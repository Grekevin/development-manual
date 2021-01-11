* [HTML手册](#html手册)
	* [属性](#属性)
		* [background 属性](#background-属性)
			* [background-image 属性](#background-image-属性)

# HTML手册

## 属性

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

