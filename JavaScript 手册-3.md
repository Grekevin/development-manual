

# JavaScript 手册-3
### JavaScript 数组迭代方法

数组迭代方法对每个数组项进行操作。

**Array.forEach()**

forEach() 方法为每个数组元素调用一次函数（回调函数）, 不修改原数组。

该函数可接受 3 个参数：

 - 项目值(value)
 - 项目索引(index)，可省略
 - 数组本身(array)， 可省略

> 当回调函数仅使用 value 参数时，可以省略索引和数组参数

``` javascript
var txt = "";
var numbers = [45, 4, 9, 16, 25];
numbers.forEach(myFunction);

function myFunction(value, index, array) {
  txt = txt + value + "<br>"; 
}

//省略项目索引(index)和数组本身(array)
function myFunction(value) {
  txt = txt + value + "<br>"; 
}
```

**Array.map()**

map() 方法通过对每个数组元素执行函数来创建新数组, 不会更改原始数组数组。

map() 方法不会对没有值的数组元素执行函数。

该函数可接受 3 个参数：

 - 项目值(value)
 - 项目索引(index)，可省略
 - 数组本身(array)， 可省略

> 当回调函数仅使用 value 参数时，可以省略索引和数组参数

下面这个例子将每个数组值乘以2：

``` javascript
var numbers1 = [45, 4, 9, 16, 25];
var numbers2 = numbers1.map(myFunction);	//90,8,18,32,50

function myFunction(value, index, array) {
  return value * 2;
  }
  
//省略项目索引(index)和数组本身(array)  
function myFunction(value) {
  return value * 2;
}
```

**Array.filter()**

filter() 方法创建一个包含通过测试的数组元素的新数组。

函数可接受 3 个参数：

 - 项目值(value)
 - 项目索引(index)，可省略
 - 数组本身(array)， 可省略

> 回调函数不使用 index 和 array 参数，因此可以省略它们

下面这个例子用值大于 18 的元素创建一个新数组：

``` javascript
var numbers = [45, 4, 9, 16, 25];
var over18 = numbers.filter(myFunction);

function myFunction(value, index, array) {
  return value > 18;
}

//省略项目索引(index)和数组本身(array)
function myFunction(value) {
  return value > 18;
}
```
**Array.reduce()**

reduce() 方法在每个数组元素上运行函数，以生成（减少它）单个值。

reduce() 方法在数组中从左到右工作。

reduce() 方法不会减少原始数组。

此函数接受 4 个参数：

 - 总数（初始值/先前返回的值），不提供初始值则为第一个数组元素的值
 - 项目值，未使用可省略
 - 项目索引，未使用可省略
 - 数组本身， 未使用可省略

这个例子确定数组中所有数字的总和：

``` javascript
var numbers1 = [45, 4, 9, 16, 25];
var sum = numbers1.reduce(myFunction);

function myFunction(total, value, index, array) {
  return total + value;
}

//省略index和array
function myFunction(total, value) {
  return total + value;
}
```
reduce() 方法能够接受一个初始值， 如果未提供初始值，total的初始值是从数组左侧开始的第一个元素的值：

``` javascript
var numbers1 = [45, 4, 9, 16, 25];
var sum = numbers1.reduce(myFunction, 100);

function myFunction(total) {
  return total;	//total = 100
}

var sum = numbers1.reduce(myFunction,);

function myFunction(total) {
  return total;	//total = 45
}
```

**Array.reduceRight()**

reduceRight() 方法在每个数组元素上运行函数，以生成（减少它）单个值。

reduce() 方法在数组中从右到左工作。

reduce() 方法不会减少原始数组。

此函数接受 4 个参数：

 - 总数（初始值/先前返回的值），不提供初始值则为第一个数组元素的值
 - 项目值，未使用可省略
 - 项目索引，未使用可省略
 - 数组本身， 未使用可省略

这个例子确定数组中所有数字的总和：

``` javascript
var numbers1 = [45, 4, 9, 16, 25];
var sum = numbers1.reduceRight(myFunction);

function myFunction(total, value, index, array) {
  return total + value;
}

//省略index和array
function myFunction(total, value) {
  return total + value;
}
```
reduceRight() 方法能够接受一个初始值， 如果未提供初始值，total的初始值是从数组右边开始的第一个元素的值：

``` javascript
var numbers1 = [45, 4, 9, 16, 25];
var sum = numbers1.reduceRight(myFunction, 100);

function myFunction(total) {
  return total;	//total = 100
}

var sum = numbers1.reduceRight(myFunction,);

function myFunction(total) {
  return total;	//total = 25
}
```
**Array.every()和 Array.some()**

> Array.some()和Array.every()用法类似，区别在于：Array.some()只要数组元素有一个测试是true就会返回true；否则false。

every() 方法检查所有数组值是否通过测试， 返回值是布尔类型的：true或false。
只有数组所有元素测试都是true时，才会返回true；否则false。

请注意此函数接受 3 个参数：

 - 项目值
 - 项目索引
 - 数组本身

> 如果回调函数仅使用第一个参数（值）时，可以省略其他参数

下面这个例子检查所有数组值是否大于 18：

``` javascript
var numbers = [45, 4, 9, 16, 25];
var allOver18 = numbers.every(myFunction);

function myFunction(value, index, array) {
  return value > 18;
}

//省略index和array
function myFunction(value) {
  return value > 18;
}
```

**Array.indexOf()**

indexOf() 方法在数组中搜索元素值并返回在数组中可以找到一个给定元素的第一个索引，如果不存在，则返回-1。

> 注释：从左向右：第一个项目的位置是 0，第二个项目的位置是 1，以此类推。

`indexOf` 使用[strict equality](https://developer.mozilla.org/zh-CN/docs/Web/JavaScript/Reference/Operators/Comparison_Operators#Using_the_Equality_Operators) (无论是 ===, 还是 triple-equals操作符都基于同样的方法)进行判断 `item`与数组中包含的元素之间的关系。

**语法**

``` javascript
array.indexOf(item, start)
```

| item | 必需。要检索的项目。 |
| --- | --- |
| start | 可选。开始查找的位置。如果该索引值大于或等于数组长度，意味着不会在数组里查找，返回-1。如果参数中提供的索引值是一个负值，则将其作为数组末尾的一个抵消，即-1表示从最后一个元素开始查找，-2表示从倒数第二个元素开始查找 ，以此类推。 注意：如果参数中提供的索引值是一个负值，并不改变其查找顺序，查找顺序仍然是从前向后查询数组。如果抵消后的索引值仍小于0，则整个数组都将会被查询。其默认值为0. |

如果未找到项目，Array.indexOf() 返回 -1。

如果项目多次出现，则返回第一次出现的位置。

``` javascript
var fruits = ["Apple", "Orange", "Apple", "Mango"];
var a = fruits.indexOf("Apple");	//0

var a = fruits.indexOf("Apple", -3);	//2
```

**Array.lastIndexOf()**

Array.lastIndexOf() 与 Array.indexOf() 类似，但是从数组结尾开始搜索，返回数组中该元素最后一次出现的索引，如未找到返回-1。

lastIndexOf 使用严格相等（strict equality，即 ===）比较。

``` javascript
array.lastIndexOf(item, start)
```
| item | 必需。要检索的项目。 |
| --- | --- |
| start | 可选。从此位置开始逆向查找。默认为数组的长度减 1(arr.length - 1)，即整个数组都被查找。如果该值大于或等于数组的长度，则整个数组会被查找。如果为负值，将其视为从数组末尾向前的偏移。即使该值为负，数组仍然会被从后向前查找。如果该值为负时，其绝对值大于数组长度，则方法返回 -1，即数组不会被查找。 |

``` javascript
var fruits = ["Apple", "Orange", "Apple", "Mango"];
var a = fruits.lastIndexOf("Apple");  //2

var a = fruits.lastIndexOf("Apple", -3);	//0
```

