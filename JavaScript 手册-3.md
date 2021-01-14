

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

indexOf() 方法在数组中搜索元素值并返回其位置。

> 注释：从左向右：第一个项目的位置是 0，第二个项目的位置是 1，以此类推。

**语法**

``` javascript
array.indexOf(item, start)
```

| item | 必需。要检索的项目。 |
| --- | --- |
| start | 可选。从哪里开始搜索。负值将从结尾开始的给定位置开始，并搜索到结尾。 |

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
| start | 可选。从哪里开始搜索。负值将从结尾开始的给定位置开始，并搜索到开头。 |

``` javascript
var fruits = ["Apple", "Orange", "Apple", "Mango"];
var a = fruits.lastIndexOf("Apple");  //2

var a = fruits.lastIndexOf("Apple", -3);	//1
```