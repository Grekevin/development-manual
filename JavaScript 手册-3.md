

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

reduce() 方法在数组中从左到右工作。另请参见 reduceRight（）。

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
reduce() 方法能够接受一个初始值， 如果未提供初始值，total的初始值是第一个元素的值：

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

