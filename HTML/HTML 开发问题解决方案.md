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


