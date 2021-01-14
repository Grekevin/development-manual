

# JavaScript 手册-3
### JavaScript 数组迭代方法

数组迭代方法对每个数组项进行操作。

**Array.forEach()**

forEach() 方法为每个数组元素调用一次函数（回调函数）, 不修改原数组。

``` javascript
var txt = "";
var numbers = [45, 4, 9, 16, 25];
numbers.forEach(myFunction);

function myFunction(value, index, array) {
  txt = txt + value + "<br>"; 
}
```

注释：该函数接受 3 个参数：

 - 项目值
 - 项目索引
 - 数组本身

上面的例子只用了 value 参数。这个例子可以重新写为：

``` javascript
var txt = "";
var numbers = [45, 4, 9, 16, 25];
numbers.forEach(myFunction);

function myFunction(value) {
  txt = txt + value + "<br>"; 
}
```

