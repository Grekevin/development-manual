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

