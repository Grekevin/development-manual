* [HTML](#html)
	* [标签](#标签)
		* [常见问题](#常见问题)
			* [div元素对于连续的英文或数字不会自动换行，中文可以自动换行](#div元素对于连续的英文或数字不会自动换行中文可以自动换行)

# HTML
## 标签
### 常见问题
####  div元素对于连续的英文或数字不会自动换行，中文可以自动换行

> 连续英文字母或连续数字在div、p、h2、h1等盒子里排成一排显示不会自动随盒子宽度限制而自动换行；中文不会出现这样的问题。

示例代码：

``` html
<!DOCTYPE html>
<html>
<head>
	<title>Flexibal Box Layout</title>

	<style type="text/css">
		div {
			height: 200px;
			width: 200px;
			background-color: red; 
			margin: 20px;
		}
	</style>
</head>
<body>
	<div>1111111111111111111111111111111111111111111111111111111111111111111111111111111111111</div>
	<div>kdfkdkvkvmdhvkckvnmchvkckxnckshjchdvjdgvhdhvhdcbbbchcdcbdbcdjcvjdvbjvbdj</div>
	<div>我我我我我我我我我我我我我我我我我我我我我我我我我我我我我我我我我我我我我我我我</div>
</body>
</html>
```
效果示例:

![示例代码](https://raw.githubusercontent.com/Grekevin/development-manual-imgs/master/1616470535359.png)


中文字在div中均会自动换行不需要css样式实现，只有连续的字母或数字会出现不自动换行问题，所以需要css解决。

解决方案：

> word-wrap:break-word

解释：使用break-word时，是将强制换行。

兼容各版本IE浏览器，兼容谷歌浏览器。

示例代码：

```html
<!DOCTYPE html>
<html>
<head>
	<title>Flexibal Box Layout</title>

	<style type="text/css">
		div {
			height: 200px;
			width: 200px;
			background-color: red; 
			margin: 20px;
			word-wrap: break-word;
		}
	</style>
</head>
<body>
	<div>1111111111111111111111111111111111111111111111111111111111111111111111111111111111111</div>
	<div>kdfkdkvkvmdhvkckvnmchvkckxnckshjchdvjdgvhdhvhdcbbbchcdcbdbcdjcvjdvbjvbdj</div>
</body>
</html>
```
效果示例：
![强制换行示例](https://raw.githubusercontent.com/Grekevin/development-manual-imgs/master/1616470814412.png)