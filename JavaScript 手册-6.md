# JavaScript 手册-6

### JavaScript 调试

**JavaScript 调试**

在没有调试器的情况下写 JavaScript 是有难度的。

您的代码中也许包含了语法错误，或者逻辑错误，这些都难以诊断。

通常，如果 JavaScript 代码包含错误，也不会发生任何事情。不会有错误消息，并且不会有任何可供查找错误的指示信息。

通常，每当你尝试编写新的 JavaScript 代码，就可能发生错误。

**JavaScript 调试器**

查找编程代码中的错误被称为代码调试。

调试并不简单。但幸运地是，所有现代浏览器都有内置的调试器。

内置的调试器可打开或关闭，强制将错误报告给用户。

通过调试器，您也可以设置断点（代码执行被中断的位置），并在代码执行时检查变量。

通常通过 F12 键启动浏览器中的调试器，然后在调试器菜单中选择“控制台”。

**console.log() 方法**

如果您的浏览器支持调试，那么您可以使用 console.log() 在调试窗口中显示 JavaScript 的值：

``` javascript
<script>
a = 5;
b = 6;
c = a + b;
console.log(c);
</script>
```

**设置断点**

在调试窗口中，您可在 JavaScript 代码中设置断点。

在每个断点中，JavaScript 将停止执行，以使您能够检查 JavaScript 的值。

在检查值之后，您可以恢复代码执行。

**debugger 关键词**

debugger 关键词会停止 JavaScript 的执行，并调用（如果有）调试函数。

这与在调试器中设置断点的功能是一样的。

如果调试器不可用，debugger 语句没有效果。

如果调试器已打开，此代码会在执行第三行之前停止运行。

``` javascript
var x = 15 * 5;
debugger;
document.getElementbyId("demo").innerHTML = x; 
```

