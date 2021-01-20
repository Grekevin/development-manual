
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

