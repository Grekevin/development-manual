# JavaScript 手册-4

### JavaScript Math 对象

``` javascript
Math.PI;	//3.141592653589793

//Math.round(x) 的返回值是 x 四舍五入为最接近的整数
Math.round(6.8);    // 返回 7
Math.round(2.3);    // 返回 2

//Math.pow(x, y) 的返回值是 x 的 y 次幂
Math.pow(8, 2); // 返回 64

//Math.sqrt(x) 返回 x 的平方根
Math.sqrt(64);      // 返回 8

//Math.abs(x) 返回 x 的绝对（正）值
Math.abs(-4.7);     // 返回 4.7

//Math.ceil(x) 的返回值是 x 上舍入最接近的整数
Math.ceil(6.4);     // 返回 7

//Math.floor(x) 的返回值是 x 下舍入最接近的整数
Math.floor(2.7);    // 返回 2

//Math.min() 和 Math.max() 可用于查找参数列表中的最低或最高值
Math.min(0, 450, 35, 10, -8, -300, -78);  // 返回 -300
Math.max(0, 450, 35, 10, -8, -300, -78);  // 返回 450

//Math.random() 返回介于 0（包括） 与 1（不包括） 之间的随机数
Math.random();     // 返回随机数
```

**Math.sin()**

Math.sin(x) 返回角 x（以弧度计）的正弦（介于 -1 与 1 之间的值）。

如果您希望使用角度替代弧度，则需要将角度转换为弧度：

``` javascript
Angle in radians = Angle in degrees x PI / 180.
```

``` javascript
Math.sin(90 * Math.PI / 180);     // 返回 1（90 度的正弦）
```

**Math.cos()**

Math.cos(x) 返回角 x（以弧度计）的余弦（介于 -1 与 1 之间的值）。

如果您希望使用角度替代弧度，则需要将角度转换为弧度：

``` javascript
Angle in radians = Angle in degrees x PI / 180.
```

``` javascript
Math.cos(0 * Math.PI / 180);     // 返回 1（0 度的余弦）
```

**Math 属性（常量）**

JavaScript 提供了可由 Math 对象访问的 8 个数学常量：

``` javascript
Math.E          // 返回欧拉指数（Euler's number）
Math.PI         // 返回圆周率（PI）
Math.SQRT2      // 返回 2 的平方根
Math.SQRT1_2    // 返回 1/2 的平方根
Math.LN2        // 返回 2 的自然对数
Math.LN10       // 返回 10 的自然对数
Math.LOG2E      // 返回以 2 为底的 e 的对数（约等于 1.414）
Math.LOG10E     // 返回以 10 为底的 e 的对数（约等于0.434）
```

**Math 构造器**

与其他全局对象不同，Math对象没有构造函数。方法和属性是静态的。

可以在不首先创建Math对象的情况下使用所有方法和属性（常量）。

### Math 对象方法

| 方法 | 描述 |
| --- | --- |
| abs(x) | 返回 x 的绝对值 |
| acos(x) | 返回 x 的反余弦值，以弧度计 |
| asin(x) | 返回 x 的反正弦值，以弧度计 |
| atan(x) | 以介于 -PI/2 与 PI/2 弧度之间的数值来返回 x 的反正切值。 |
| atan2(y,x) | 返回从 x 轴到点 (x,y) 的角度 |
| ceil(x) | 对 x 进行上舍入 |
| cos(x) | 返回 x 的余弦 |
| exp(x) | 返回 Ex 的值 |
| floor(x) | 对 x 进行下舍入 |
| log(x) | 返回 x 的自然对数（底为e） |
| max(x,y,z,...,n) | 返回最高值 |
| min(x,y,z,...,n) | 返回最低值 |
| pow(x,y) | 返回 x 的 y 次幂 |
| random() | 返回 0 ~ 1 之间的随机数 |
| round(x) | 把 x 四舍五入为最接近的整数 |
| sin(x) | 返回 x（x 以角度计）的正弦 |
| sqrt(x) | 返回 x 的平方根 |
| tan(x) | 返回角的正切 |

### JavaScript 随机

**Math.random()**

Math.random() 返回 0（包括） 至 1（不包括） 之间的随机数：

``` javascript
Math.random();				// 返回随机数
```

> Math.random() 总是返回小于 1 的数。

**JavaScript 随机整数**

Math.random() 与 Math.floor() 一起使用用于返回随机整数。

``` javascript
Math.floor(Math.random() * 10);		// 返回 0 至 9 之间的数
Math.floor(Math.random() * 11);		// 返回 0 至 10 之间的数
Math.floor(Math.random() * 100);	// 返回 0 至 99 之间的数
Math.floor(Math.random() * 101);	// 返回 0 至 100 之间的数

Math.floor(Math.random() * 100) + 1;	// 返回 1 至 100 之间的数
Math.floor(Math.random() * 10) + 1;	// 返回 1 至 10 之间的数
```

**一个适当的随机函数**

创建一个随机函数用于生成所有随机整数是一个好主意。

这个 JavaScript 函数始终返回介于 min（包括）和 max（不包括）之间的随机数：

``` javascript
function getRndInteger(min, max) {
    return Math.floor(Math.random() * (max - min) ) + min;
}
```

这个 JavaScript 函数始终返回介于 min 和 max（都包括）之间的随机数：

``` javascript
function getRndInteger(min, max) {
    return Math.floor(Math.random() * (max - min + 1) ) + min;
}
```

### JavaScript 逻辑

JavaScript 布尔（逻辑）代表两个值之一：true 或 false。

**布尔值**

通常，在编程中，您会需要只能有两个值之一的数据类型，比如

 - YES / NO
 - ON / OFF
 - TRUE / FALSE

鉴于此，JavaScript 提供一种布尔数据类型。它只接受值 true 或 false。

**Boolean() 函数**

您可以使用 Boolean() 函数来确定表达式（或变量）是否为真：

``` javascript
Boolean(10 > 9)        // 返回 true
```
或者甚至更简单：

``` javascript
(10 > 9)              // 也返回 true
10 > 9                // 也返回 true
```

**所有具有“真实”值的即为 True**

``` javascript
100

3.14

-15

"Hello"

"false"

7 + 1 + 3.14

5 < 6
```
**所有不具有“真实”值的即为 False**

 - 0（零）的布尔值为 false
 - -0 （负零）的布尔值为 false
 - ""（空值）的布尔值为 false
 - undefined 的布尔值是 false
 - null 的布尔值是 false
 - false 的布尔值是 false
 - NaN 的布尔值是 false

 **布尔可以是对象**
 
通常 JavaScript 布尔是由字面量创建的原始值：

``` javascript
var x = false
```

但是布尔也可以通过关键词 new 作为对象来定义：

``` javascript
var y = new Boolean(false)
```
示例：

``` javascript
var x = false;
var y = new Boolean(false);

// typeof x 返回 boolean
// typeof y 返回 object
```

不要创建布尔对象。它会拖慢执行速度。

new 关键词会使代码复杂化，并产生某些意想不到的结果：

当使用 == 运算符时，相等的布尔是相等的：

``` javascript
var x = false;             
var y = new Boolean(false);

// (x == y) 为 true，因为 x 和 y 拥有相等的值
```

当使用 === 运算符时，相等的布尔是不相等的，因为 === 运算符需要在类型和值两方面同时相等。

``` javascript
var x = false;             
var y = new Boolean(false);

// (x === y) 为 false，因为 x 和 y 的类型不同
```

或者甚至更糟。对象无法进行比较：

``` javascript
var x = new Boolean(false);             
var y = new Boolean(false);

// (x == y) 为 false，因为对象无法比较
```

> 比较两个 JavaScript 对象将始终返回 false。
