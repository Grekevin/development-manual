

# JavaScript 手册-7

### JavaScript 性能

**减少循环中的活动**

编程经常会用到循环。

循环每迭代一次，循环中的每条语句，包括 for 语句，都会被执行。

能够放在循环之外的语句或赋值会使循环运行得更快。

差的代码：

``` javascript
var i;
for (i = 0; i < arr.length; i++) {}
```

更好的代码：

``` javascript
var i;
var l = arr.length;
for (i = 0; i < l; i++) {}
```

循环每次迭代时，坏代码就会访问数组的 length 属性。

好代码在循环之外访问 length 属性，使循环更快。

### 