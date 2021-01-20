
# JS JSON

## JSON 简介

> JSON: JavaScript Object Notation（JavaScript 对象标记法）。
JSON 是一种存储和交换数据的语法。
JSON 是通过 JavaScript 对象标记法书写的文本。

### 交换数据

当数据在浏览器与服务器之间进行交换时，这些数据只能是文本。

JSON 属于文本，并且我们能够把任何 JavaScript 对象转换为 JSON，然后将 JSON 发送到服务器。

我们也能把从服务器接收到的任何 JSON 转换为 JavaScript 对象。

以这样的方式，我们能够把数据作为 JavaScript 对象来处理，无需复杂的解析和转译。

### 发送数据

如果您的数据存储在 JavaScript 对象中，您可以把该对象转换为 JSON，然后将其发送到服务器。

``` javascript
var myObj = { name:"Bill Gates",  age:62, city:"Seattle" };
var myJSON =  JSON.stringify(myObj);
window.location = "demo_json.php?x=" + myJSON;
```

### 接收数据

如果您以 JSON 格式接收到数据，您能够将其转换为 JavaScript 对象：

``` javascript
var myJSON = '{ "name":"Bill Gates",  "age":62, "city":"Seattle" }';
var myObj =  JSON.parse(myJSON);
document.getElementById("demo").innerHTML = myObj.name;
```

### 存储数据

在存储数据时，数据必须是某种具体的格式，并且无论您选择在何处存储它，文本永远是合法格式之一。

JSON 让 JavaScript 对象存储为文本成为可能。

把数据存储在本地存储中

``` javascript
//存储数据：
myObj = { name:"Bill Gates",  age:62, city:"Seattle" };
myJSON =  JSON.stringify(myObj);
localStorage.setItem("testJSON", myJSON);

//接收数据：
text = localStorage.getItem("testJSON");
obj =  JSON.parse(text);
document.getElementById("demo").innerHTML = obj.name;
```

### 什么是 JSON？

 - JSON 指的是 JavaScript 对象标记法（JavaScript Object Notation）
 - JSON 是一种轻量级的数据交换格式
 - JSON 具有自我描述性且易于理解
 - JSON 独立于语言

JSON 使用 JavaScript 语法，但是 JSON 格式是纯文本的。

文本可被任何编程语言作为数据来读取和使用。

JSON 格式最初由 Douglas Crockford 提出。

### 为什么使用 JSON？

因为 JSON 格式仅仅是文本，它能够轻松地在服务器浏览器之间传输，并用作任何编程语言的数据格式。

JavaScript 提供內建函数把以 JSON 格式写的字符串转换为原生 JavaScript 对象：

``` javascript
JSON.parse()
```

因此，如果您以 JSON 格式从服务器接收数据，那么您可以像任何其他 JavaScript 对象那样使用它。

