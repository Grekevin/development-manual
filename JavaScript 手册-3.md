

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

**Array.find()和Array.findIndex()**

> Array.findIndex()和Array.find()用类似，只不过返回的是找的元素的索引值。

find() 方法返回通过测试函数的第一个数组元素的值。

请注意此函数接受 3 个参数：

 - 项目值
 - 项目索引(可省略)
 - 数组本身(可省略)

例子查找（返回）大于 18 的第一个元素的值：

``` javascript
var numbers = [4, 9, 16, 25, 29];
var first = numbers.find(myFunction);	//25

function myFunction(value, index, array) {
  return value > 18;
}

//等效
function myFunction(value) {
  return value > 18;
}
```

### JavaScript 日期

实例

``` javascript
var d = new Date();
```

**JavaScript 日期输出**

默认情况下，JavaScript 将使用浏览器的时区并将日期显示为全文本字符串：

``` javascript
Thu Jan 14 2021 13:28:40 GMT+0800 (China Standard Time)
```

**创建 Date 对象**

Date 对象由新的 Date() 构造函数创建。

有 4 种方法创建新的日期对象：

 - new Date()
 - new Date(year, month, day, hours, minutes, seconds, milliseconds)
 - new Date(milliseconds)
 - new Date(date string)

**new Date()**

new Date() 用当前日期和时间创建新的日期对象：

日期对象是静态的。计算机时间正在滴答作响，但日期对象不会。

``` javascript
<script>
var d = new Date();

// d = "Thu Jan 14 2021 13:32:47 GMT+0800 (China Standard Time)"
document.getElementById("demo").innerHTML = d;
</script>
```

**new Date(year, month, ...)**

new Date(year, month, ...) 用指定日期和时间创建新的日期对象。

7个数字分别指定年、月、日、小时、分钟、秒和毫秒（按此顺序）：

``` javascript
var d = new Date(2018, 11, 24, 10, 33, 30, 0);
```

注释：JavaScript 从 0 到 11 计算月份。

一月是 0。十二月是11。


6个数字指定年、月、日、小时、分钟、秒：

``` javascript
var d = new Date(2018, 11, 24, 10, 33, 30);
```

5个数字指定年、月、日、小时和分钟：

``` javascript
var d = new Date(2018, 11, 24, 10, 33);
```

4个数字指定年、月、日和小时：

``` javascript
var d = new Date(2018, 11, 24, 10);
```

3 个数字指定年、月和日：

``` javascript
var d = new Date(2018, 11, 24);
```

2个数字指定年份和月份：

``` javascript
var d = new Date(2018, 11);
```

您不能省略月份。如果只提供一个参数，则将其视为毫秒。

``` javascript
var d = new Date(2018);
```

**new Date(dateString)**

new Date(dateString) 从日期字符串创建一个新的日期对象：

``` javascript
//Wed Dec 25 2019 12:46:00 GMT+0800 (China Standard Time)
var d = new Date("October 13, 2014 11:13:00");
```

**JavaScript 将日期存储为毫秒**

JavaScript 将日期存储为自 1970 年 1 月 1 日 00:00:00 UTC（协调世界时）以来的毫秒数。

零时间是 1970 年 1 月 1 日 00:00:00 UTC。

现在的时间是：1970 年 1 月 1 日之后的毫秒数。

**new Date(milliseconds)**

new Date(milliseconds) 创建一个零时加毫秒的新日期对象：

``` javascript
//Thu Jan 01 1970 08:00:00 GMT+0800 (China Standard Time)
var d = new Date(0);
```

1970年 1 月 1 日加上100 000 000 000毫秒，大约是 1973 年 3 月 3 日：

``` javascript
//Sat Mar 03 1973 17:46:40 GMT+0800 (China Standard Time)
var d = new Date(100000000000);
```

1970 年 1 月 1 日减去 100 000 000 000 毫秒大约是 1966 年 10 月 31 日：

``` javascript
//Mon Oct 31 1966 22:13:20 GMT+0800 (China Standard Time)
var d = new Date(-100000000000);
```

一天（24 小时）是 86 400 000 毫秒：

``` javascript
//Fri Jan 02 1970 08:00:00 GMT+0800 (China Standard Time)
var d = new Date(86400000);
```

**日期方法**

创建 Date 对象时，可以使用许多方法对其进行操作。

日期方法允许您使用本地时间或 UTC（通用或 GMT）时间来获取和设置日期对象的年、月、日、小时、分钟、秒和毫秒。

**显示日期**

JavaScript（默认情况下）将以全文本字符串格式输出日期：

在 HTML 中显示日期对象时，会使用 toString() 方法自动转换为字符串。

``` javascript
d = new Date();

//Thu Jan 14 2021 13:47:46 GMT+0800 (China Standard Time)
document.getElementById("demo").innerHTML = d;
```

等同于：

``` javascript
d = new Date();

//Thu Jan 14 2021 13:48:02 GMT+0800 (China Standard Time)
document.getElementById("demo").innerHTML = d.toString();
```

toUTCString() 方法将日期转换为 UTC 字符串（一种日期显示标准）。

``` javascript
var d = new Date();

//Thu, 14 Jan 2021 05:48:19 GMT
document.getElementById("demo").innerHTML = d.toUTCString();
```

toDateString() 方法将日期转换为更易读的格式：

``` javascript
var d = new Date();

//Thu Jan 14 2021
document.getElementById("demo").innerHTML = d.toDateString();
```

### JavaScript 日期格式化

有四种 JavaScript 日期输入格式：

| 类型 | 实例 |
| --- | --- |
| ISO 日期 | "2018-02-19" （国际标准） |
| 短日期 | "02/19/2018" 或者 "2018/02/19" |
| 长日期 | "Feb 19 2018" 或者 "19 Feb 2019" |
| 完整日期 | "Monday February 25 2015" |

ISO 格式遵守 JavaScript 中的严格标准。

其他格式不太明确，可能是浏览器特定的。

**JavaScript 日期输出**

无论输入格式如何，JavaScript 默认将输出全文本字符串格式：

Mon Feb 19 2018 06:00:00 GMT+0800 (中国标准时间)

**JavaScript ISO 日期**

ISO 8601 是表现日期和时间的国际标准。

ISO 8601 语法 (YYYY-MM-DD) 也是首选的 JavaScript 日期格式：

``` javascript
//Thu May 02 2019 08:00:00 GMT+0800 (China Standard Time)
var d = new Date("2019-05-02");
```

计算的日期相对于您的时区。

**ISO 日期（年和月）**

写日期也可以不规定具体某日 (YYYY-MM)：

``` javascript
//Fri Mar 01 2019 08:00:00 GMT+0800 (China Standard Time)
var d = new Date("2019-03");
```
**ISO 日期（只有年）**

写日期也可以不规定具体的月和日 (YYYY)：

``` javascript
//Fri Jan 01 2021 08:00:00 GMT+0800 (China Standard Time)
var d = new Date("2021");
```

**ISO 日期（完整的日期加时、分和秒）**

写日期也可以添加时、分和秒 (YYYY-MM-DDTHH:MM:SS)：



``` javascript
//Thu May 02 2019 20:00:00 GMT+0800 (China Standard Time)
var d = new Date("2019-05-02T12:00:00Z");

//Thu May 02 2019 12:00:00 GMT+0800 (China Standard Time)
var d = new Date("2019-05-02T12:00:00Z");
```
日期和时间通过大写字母 T 来分隔。

UTC 时间通过大写字母 Z 来定义。

如果您希望修改相对于 UTC 的时间，请删除 Z 并用 +HH:MM 或 -HH:MM 代替：

``` javascript
//Thu Mar 26 2015 02:00:00 GMT+0800 (China Standard Time)
var d = new Date("2015-03-25T12:00:00-06:00");
```
UTC（Universal Time Coordinated）等同于 GMT（格林威治时间）。

注释：UTC，协调世界时，又称世界统一时间，世界标准时间，国际协调时间。

在日期-时间字符串中省略 T 或 Z，在不同浏览器中会产生不同结果。

**时区**

在设置日期时，如果不规定时区，则 JavaScript 会使用浏览器的时区。

当获取日期时，如果不规定时区，则结果会被转换为浏览器时区。

换句话说，假如日期/时间以 GMT（格林威治标准时间）创建，该日期/时间将被转换为 CST（中国标准时间），如果用户从中国进行浏览。

**JavaScript 短日期**

短日期通常使用 "MM/DD/YYYY" 这样的语法：

``` javascript
//Sun May 26 2019 00:00:00 GMT+0800 (China Standard Time)
var d = new Date("05/26/2019");
```
警告: 在某些浏览器中，不带前导零的月或其会产生错误。

**JavaScript 长日期**

长日期通常以 "MMM DD YYYY" 这样的语法来写：

``` javascript
var d = new Date("Feb 19 2018");
```

月和天能够以任意顺序出现：

``` javascript
var d = new Date("19 Feb 2018");
```

并且，月能够以全称 (January) 或缩写 (Jan) 来写：

``` javascript
var d = new Date("February 19 2018");
var d = new Date("Feb 19 2018");
```

逗号会被忽略，且对大小写不敏感：

``` javascript
var d = new Date("FEBRUARY, 25, 2015");
```

**JavaScript 完整日期**

JavaScript 接受“完整 JavaScript 格式”的日期字符串：

``` javascript
var d = new Date("Mon Feb 19 2018 06:55:23 GMT+0100 (W. Europe Standard Time)");
```

JavaScript 会忽略日期名称和时间括号中的错误：

``` javascript
//Mon Mar 26 2018 16:56:24 GMT+0800 (China Standard Time)
var d = new Date("Fri Mar 26 2018 09:56:24 GMT+0100 (Tokyo Time)");
```

### JavaScript 获取日期方法

日期方法允许您获取并设置日期值（年、月、日、时、分、秒、毫秒）

**日期获取方法**

获取方法用于获取日期的某个部分（来自日期对象的信息）。下面是最常用的方法（以字母顺序排序）：

| 方法 | 描述 |
| --- | --- |
| getDate() | 以数字（1-31）返回日期的日 |
| getDay() | 以数字（0-6）返回日期的星期名（weekday） |
| getFullYear() | 以四位数字形式返回日期年份（yyyy） |
| getHours() | 以数字（0-23）返回日期的小时数 |
| getMilliseconds() | 以数字（0-999）返回日期的毫秒数 |
| getMinutes() | 以数字（0-59）返回日期的分钟数 |
| getMonth() | 以数字（0-11）返回日期的月份 |
| getSeconds() | 以数字（0-59）返回日期的秒数 |
| getTime() | 获取时间（从 1970 年 1 月 1 日至今毫秒数） |

``` javascript
//测试时间2021-1-14 14:29：00 左右
var d = new Date();
d.getTime()	;	//1610605225518
d.getFullTear();	//2021
d.getMonth();	//0
d.getDate();	//14
d.getHours();	//14
d.getMinutes();		//31
d.getSeconds();		//27
d.getMilliseconds();	//8
d.getDay();		//4

```

**getMonth() 方法**

在 JavaScript 中，第一个月（1 月）是月号 0，因此 12 月返回月号 11。

您可以使用名称数组，并使用 getMonth() 将月份作为名称返回：

``` javascript
var d = new Date();
var months = 
            [
            "January", "February", "March", "April", "May", "June", 
            "July", "August", "September", "October", "November", "December"
            ];
document.getElementById("demo").innerHTML = months[d.getMonth()];
```

通过加1来获取正确月份：

``` javascript
<script>
var d = new Date();

//getMonth（）方法以 0 到 11 之间的数字返回日期的月份。
//要获得正确的月份，您必须添加 1
document.getElementById("demo").innerHTML = d.getMonth() + 1;
</script>
```

**getDay() 方法**

getDay() 方法以数字（0-6）返回日期的星期名（weekday）：

在 JavaScript 中，一周的第一天（0）表示“星期日”，即使世界上的一些国家认为周的第一天是“星期一”。

可以使用名称数组，并使用 getDay() 将星期名作为名称返回：

``` javascript
var d = new Date();
var days = ["Sunday", "Monday", "Tuesday", "Wednesday", "Thursday", "Friday", "Saturday"];
document.getElementById("demo").innerHTML = days[d.getDay()];
```

**UTC 日期方法**

UTC 日期方法用于处理 UTC 日期（通用时区日期，Univeral Time Zone dates）：

| 方法 | 描述 |
| --- | --- |
| getUTCDate() | 等于 getDate()，但返回 UTC 日期 |
| getUTCDay() | 等于 getDay()，但返回 UTC 日 |
| getUTCFullYear() | 等于 getFullYear()，但返回 UTC 年 |
| getUTCHours() | 等于 getHours()，但返回 UTC 小时 |
| getUTCMilliseconds() | 等于 getMilliseconds()，但返回 UTC 毫秒 |
| getUTCMinutes() | 等于 getMinutes()，但返回 UTC 分 |
| getUTCMonth() | 等于 getMonth()，但返回 UTC 月 |
| getUTCSeconds() | 等于 getSeconds()，但返回 UTC 秒 |


### JavaScript 设置日期方法

使用“设置日期”方法可以设置日期对象的日期值（年、月、日、小时、分钟、秒、毫秒）。

**日期设置方法**

设置方法用于设置日期的某个部分。下面是最常用的方法（按照字母顺序排序）：

| 方法 | 描述 |
| --- | --- |
| setDate() | 以数值（1-31）设置日 |
| setFullYear() | 设置年（可选月和日） |
| setHours() | 设置小时（0-23） |
| setMilliseconds() | 设置毫秒（0-999） |
| setMinutes() | 设置分（0-59） |
| setMonth() | 设置月（0-11） |
| setSeconds() | 设置秒（0-59） |
| setTime() | 设置时间（从 1970 年 1 月 1 日至今的毫秒数） |

> JavaScript 从 0 到 11 计数月份。1 月是 0。12 月是 11。

具体使用见：

[官方使用教程](https://www.w3school.com.cn/js/js_date_methods_set.asp)

**比较日期**

日期可以很容易地进行比较。

下面的例子把今日与 2049 年 1 月 16 日进行比较：

``` javascript
var today, someday, text;
today = new Date();
someday = new Date();
someday.setFullYear(2049, 0, 16);

if (someday > today) {
  text = "今天在 2049 年 1 月 16 日之前";
} else {
  text = "今天在 2049 年 1 月 16 日之后";
}
document.getElementById("demo").innerHTML = text;
```

