* [PHP开发手册](#php开发手册)
	* [PHP基础知识](#php基础知识)
		* [介绍](#介绍)
		* [PHP 安装](#php-安装)
		* [PHP 语法](#php-语法)
		* [PHP变量](#php变量)
		* [PHP echo 和 print 语句](#php-echo-和-print-语句)
		* [PHP EOF(heredoc) 使用说明](#php-eofheredoc-使用说明)

# PHP开发手册
## PHP基础知识
[参考资料](https://www.runoob.com/php/php-tutorial.html)

### 介绍
PHP 是是免费的，一种创建动态交互性站点的强有力的服务器端脚本语言。

[学习建议及学习路线](https://www.runoob.com/w3cnote/php-learning-recommend.html)

[开发工具推荐](https://www.runoob.com/w3cnote/php-develop-tools.html)

**PHP 是什么？**
 - PHP（全称：PHP：Hypertext Preprocessor，即"PHP：超文本预处理器"）是一种通用开源脚本语言。
 - PHP 脚本在服务器上执行。
 - PHP 可免费下载使用。
   
 **PHP 文件是什么？**
 - PHP 文件可包含文本、HTML、JavaScript代码和 PHP 代码
 - PHP 代码在服务器上执行，结果以纯 HTML 形式返回给浏览器
 - PHP 文件的默认文件扩展名是 ".php"
   
**PHP 能做什么？**
 - PHP 可以生成动态页面内容
 - PHP 可以创建、打开、读取、写入、关闭服务器上的文件
 - PHP 可以收集表单数据
 - PHP 可以发送和接收 cookies
 - PHP 可以添加、删除、修改您的数据库中的数据
 - PHP 可以限制用户访问您的网站上的一些页面
 - PHP 可以加密数据

通过 PHP，您不再限于输出 HTML。您可以输出图像、PDF 文件，甚至 Flash 电影。您还可以输出任意的文本，比如 XHTML 和 XML。

**为什么使用 PHP？**

 - PHP 可在不同的平台上运行（Windows、Linux、Unix、Mac OS X 等）
 - PHP 与目前几乎所有的正在被使用的服务器相兼容（Apache、IIS 等）
 - PHP 提供了广泛的数据库支持
 - PHP 是免费的，可从官方的 PHP 资源下载它： www.php.net
 - PHP 易于学习，并可高效地运行在服务器端
  
 ### PHP 安装
您需要做什么？
为了开始使用 PHP，您可以：
 - 找一个支持 PHP 和 MySQL 的 Web 主机
 - 在您自己的 PC 机上安装 Web 服务器，然后安装 PHP 和 MySQL

**使用支持 PHP 的 Web 主机**
如果您的服务器支持 PHP，那么您不需要做任何事情。
只要在您的 web 目录中创建 .php 文件即可，服务器将自动为您解析这些文件。
您不需要编译任何软件，或安装额外的工具。
由于 PHP 是免费的，大多数的 Web 主机都提供对 PHP 的支持。

**在您自己的 PC 机上建立 PHP**
然而，如果您的服务器不支持 PHP，您必须：
 - 安装 Web 服务器
 - 安装 PHP
 - 安装数据库，比如 MySQL
   
官方 PHP 网站（PHP.net）有 PHP 的安装说明： http://php.net/manual/en/install.php

**PHP 服务器组件**

对于初学者建议使用集成的服务器组件，它已经包含了 PHP、Apache、Mysql 等服务,免去了开发人员将时间花费在繁琐的配置环境过程。

**WampServer**

Windows 系统可以使用 WampServer，下载地址：http://www.wampserver.com/，支持32位和64位系统，根据自己的系统选择版本。
WampServer 安装也简单，你只需要一直点击 "Next" 就可以完成安装了。

**XAMPP**

XAMPP 支持 Mac OS 和 Windows 系统，下载地址：https://www.apachefriends.org/zh_cn/index.html。

**IDE (Integrated Development Environment,集成开发环境)**

**Eclipse for PHP（免费）**

Eclipse 是一个开放源代码的、基于Java的可扩展开发平台(如果未安装JDK，则需要先 下载 JDK 安装)。就其本身而言，它只是一个框架和一组服务，用于通过插件组件构建开发环境。幸运的是，Eclipse 附带了一个标准的插件集，包括Java开发工具（Java Development Kit，JDK）。

支持 Windows、Linux 和 Mac OS 平台。

Eclipse for PHP 官方下载地址：http://www.eclipse.org/downloads/packages/eclipse-php-developers/heliosr

**PhpStorm（收费）**

PhpStorm是一个轻量级且便捷的PHP IDE，其旨在提供用户效率，可深刻理解用户的编码，提供智能代码补全，快速导航以及即时错误检查。

PhpStorm 非常适合于PHP开发人员及前端工程师。提供诸于：智能HTML/CSS/JavaScript/PHP编辑、代码质量分析、版本控制集成（SVN、GIT）、调试和测试等功能。

支持 Windows、Linux 和 Mac OS 平台。

PhpStorm 官方下载地址：http://www.jetbrains.com/phpstorm/download/

### PHP 语法
PHP 脚本在服务器上执行，然后将纯 HTML 结果发送回浏览器。

**基本的 PHP 语法**

PHP 脚本可以放在文档中的任何位置。

PHP 脚本以 `<?php 开始，以 ?>` 结束

>  - `<?php` ?和php之间不能有空格
>  - 结尾的?>可以省略

``` php
<?php
// PHP 代码
?>
```

>    当解析一个文件时，PHP（Hypertext Preprocessor超文本预处理器） 会寻找起始和结束标记，也就是 `<?php 和 ?>`，这告诉 PHP 开始和停止解析二者之间的代码。此种解析方式使得PHP 可以被嵌入到各种不同的文档中去，而任何起始和结束标记之外的部分都会被 PHP 解析器忽略。

   
 - PHP 文件的默认文件扩展名是 ".php"。
 - PHP 文件通常包含 HTML 标签和一些 PHP 脚本代码。

下面，我们提供了一个简单的 PHP 文件实例，它可以向浏览器输出文本 "Hello World!"：

``` php
<!DOCTYPE html>
<html>
<body>

<h1>My first PHP page</h1>

<?php
echo "Hello World!";
?>  

</body>
</html>
```
PHP 中的每个代码行都必须以分号结束。分号是一种分隔符，用于把指令集区分开来。

通过 PHP，有两种在浏览器输出文本的基础指令：echo 和 print。

**PHP 中的注释**

PHP 支持三种注释：

``` php
<!DOCTYPE html>
<html>
<body>
  
<?php
// 这是单行注释

# 这也是单行注释

/*
这是多行注释
多行注释
多行注释
*/

echo "Hello World!";
?>
  
</body>
</html>
```

### PHP变量

变量是用于存储数据（信息）的容器。

代码示例：

``` php
<?php
$a = 2;
$b = 3;
$c = $a + $b;
echo $c;
?>
```
**PHP 变量规则：**

 - 变量以 $ 符号开始，后面跟着变量的名称
 - 变量名必须以字母或者下划线字符开始
 - 变量名只能包含字母数字字符以及下划线（A-z、0-9 和 _ ）
 - 变量名不能包含空格
 - 变量名是区分大小写的（$y 和 $Y 是两个不同的变量）

> **注意**：PHP 语句和 PHP 变量都是区分大小写的。

·**创建（声明）PHP 变量**

PHP没有单独声明变量的语句

当第一给变量赋值的时候才创建变量。

``` php
<?php
$x;	# 没有这样单独的声明语句
x = 15;	# 这样赋值是错误的
	
// 必须这样声明创建变量
$x = 15;
?>
```
**PHP 是一门弱类型语言**

在上面的实例中，我们注意到，不必向 PHP 声明该变量的数据类型。

PHP 会根据变量的值，自动把变量转换为正确的数据类型。

在强类型的编程语言中，我们必须在使用变量前先声明（定义）变量的类型和名称。

**PHP 变量作用域**

变量的作用域是脚本中变量可被引用/使用的部分。

PHP 有四种不同的变量作用域：

 - local
 - global
 - static
 - parameter

**局部和全局作用域**

在所有函数外部定义的变量，拥有全局作用域。**除了函数外**，全局变量可以被脚本中的任何部分访问，要在一个函数中访问一个全局变量，需要使用 global 关键字。

在 PHP 函数内部声明的变量是局部变量，仅能在函数内部访问

示例代码：

``` php
$x = 5;  //全局变量

function test(){
	$y = 10;  //局部变量
	
	echo "<p>函数内访问全部变量x:</p>";
	echo "x = $x";   //输出 x =  函数内无法访问到全局变量的值
	echo "<br>";
	echo "y = $y";   //输出 y = 10
}
test();

echo "<p>函数外访问函数内局部变量y:</p>";
echo "y = $y";	//输出 y =  函数外无法访问到变量的值
echo "<br>";
echo "x = $x";   //输出 x = 5
```

> 可以在不同函数中使用相同的变量名称，因为这些函数内定义的变量名是局部变量，只作用于该函数内。

**PHP global 关键字**

global 关键字用于函数内访问全局变量。

当需要在函数内调用函数外定义的全局变量，需要在函数中的变量前加上 global 关键字

代码示例：

``` php
<?php
$x = 5;
$y = 6;

function add(){
	global $x, $y;
	$z = $x + $y;
	echo "z = $z";
}
add();	//输出 z = 11
?>
```

> PHP 将所有全局变量存储在一个名为 **$GLOBALS[index]** 的数组中。 index 保存变量的名称。这个数组可以在函数内部访问，也可以直接用来更新全局变量。

代码示例：

``` php
<?php
$x = 5;
$y = 6;

function updata_y(){
	// 通过$GLOBALS数组访问全局变量$x, $y, 最后通过赋值更新$y的值
	$GLOBALS['y']=$GLOBALS['x']+$GLOBALS['y'];
}
updata_y();
echo "y = $y";	//通过函数updata_y()更新了变量$y的值：y = 11
?>
```
**Static 作用域**

当一个函数完成时，它的所有变量通常都会被删除。然而，有时候您希望某个局部变量不要被删除。

要做到这一点，请在您第一次声明变量时使用 static 关键字

代码示例:

``` php
<?php
function myTest()
{
    static $x=0;	//每次调用该函数时，该变量将会保留着函数前一次被调用时的值
    echo $x;
    $x++;
    echo PHP_EOL;    // 换行符
}
 
myTest();	//0
myTest();	//1
myTest();	//2	
?>
```

> 注释：static修饰的变量仍然是函数的局部变量

**参数作用域**

参数是通过调用代码将值传递给函数的局部变量。

参数是在参数列表中声明的，作为函数声明的一部分。

**总结：**

 1. 定义在函数外部的就是全局变量，它的作用域从定义处一直到文件结尾。
 2. 函数内定义的变量就是局部变量，它的作用域为函数定义范围内。
 3. 函数之间存在作用域互不影响。
 4. 函数内访问全局变量需要 global 关键字或者使用 $GLOBALS[index] 数组

变量的作用域是脚本中变量可被引用和使用的部分，PHP 中有四种不同的变量作用域:

| 序号 | 作用域 | 描述           | 说明 |
| ---- | ------ | -------------- | ---------|
| 1    | local  | 局部作用域  | 函数内声明的变量是局部变量，仅能在函数内部访问 |
| 2    | global | 全局作用域  | 在所有函数外部定义的变量是全局变量，除了函数外，全局变量可以被脚本中的任何部分访问、要在一个函数中访问一个全局变量，需要使用 global 关键字 |
| 3    | static  | 静态作用域  | 该变量会保留上一次函数调用结束时最后存储的值 |
| 4    |  parameter  | 函数参数作用域 | 参数是通过调用代码将值传递给函数的局部变量 |

### PHP echo 和 print 语句

echo 和 print 区别:

 - echo - 可以输出一个或多个字符串
 - print - 只允许输出一个字符串，返回值总为 1

> 提示：echo 输出的速度比 print 快， echo 没有返回值，print有返回值1。

**PHP echo 语句**

echo 是一个语言结构，使用的时候可以不用加括号，也可以加上括号： echo 或 echo()。

显示字符串

下面的实例演示了如何使用 echo 命令输出字符串（字符串可以包含 HTML 标签）：

``` php
<?php
echo "<p>Hello World</p>";	//包含HTML语句
echo "<br>";
echo("我要学 PHP!<br>");	//可以带括号
echo "<br>";
echo "这是一个", "字符串，", "使用了", "多个", "参数。";	//输出多个字符串
echo "<br>";

$txt1="学习 PHP";
$txt2="RUNOOB.COM";
$cars=array("Volvo","BMW","Toyota");
 
echo $txt1;	//输出变量
echo "<br>";
echo "在 $txt2 学习 PHP ";	//输出字符串
echo "<br>";
echo "我车的品牌是 {$cars[0]}";	//输出数组元素
?>
```
**PHP print 语句**

print 同样是一个语言结构，可以使用括号，也可以不使用括号： print 或 print()。

显示字符串

下面的实例演示了如何使用 print 命令输出字符串（字符串可以包含 HTML 标签）：

``` php
<?php
$txt1="学习 PHP";
$txt2="RUNOOB.COM";
$cars=array("Volvo","BMW","Toyota");
 
print $txt1;	//输出变量
print "<br>";
print("在 $txt2 学习 PHP ");	//输出字符串
print "<br>";
print "我车的品牌是 {$cars[0]}";	//输出数组元素
?>
```

**总结**

echo 和 print语句的区别

 1. echo 可以输出一个或多个字符串；
 2. print 只允许输出一个字符串，返回值总为 1；
 3. echo 输出的速度比 print 快；
 4. echo 没有返回值，print 有返回值 1；

``` php
$a = 9;
```

`print $a` 和 `print "$a"` 效果相同，`echo` 同理。

`print "text$a text"` 和 `print "text $a text"` 和 `print "text{$a}text"` 都可以正常显示 $a 的值，不使用 {} 则 `$a` 之后必须有一个空格，不然就无法识别变量（`"text$atext"` 会识别为变量 `$atext`）`echo` 同理。

**拓展**

`echo` 是语法结构，也就是关键字，不是函数。使用的时候不用加括号，加上也可以。显示多个值的时候可以用逗号隔开。只支持基本类型，布尔型除外，`echo true`的时候显示1，`echo false`的时候啥都没有。

`print` 和 `echo` 基本一致。但是`print` 不支持逗号分隔多个显示变量的语法。

`print_r` 是函数，**不仅可以打印变量的的值，还能显示变量类型，而且也可以显示数组和对象这样复杂的变量类型**。`print_r()` 将把数组的指针移到最后边。使用 `reset()` 可让指针回到开始处。

**两者相同点：**

 -  `echo` 和 `print` 都是语言结构(官方文档解释为language construct)；
 - `echo` 和 `print` 都是用来输出字符串的；
 - 当同时只有一个参数的时候，`echo` 和 `print` 后面的括号(parenthesis)都是可选的，即：`echo ($argument1)` 等价于 `echo $argument1`，`print(argument)`等价于`print argument`；
 - `echo` 和 `print` 在输出之前，都会将参数的进行转换，尝试转换为字符串类型。

**两者的区别：**

 - `echo`能接受N个字符串类型的参数(**注意:有多个参数的时候，不能使用括号**，即`echo $arg1,$arg2`是正确的，`echo($arg1,$arg2)`会导致解析错误)； `print`只能接收1个字符串类型的参数；
 - `echo`没有返回值； `print`有返回值，其值永远为int类型的1。
 - 在这里引用PHP官方原文档的说明 : "The major differences to echo are that print only accepts a single argument and always returns 1."

**常见的输出语句**

 - `echo():` 可以一次输出多个值，多个值之间用逗号分隔。`echo`是语言结构(language construct)，而并不是真正的函数，因此不能作为表达式的一部分使用。
 - `print()`: 函数`print()`打印一个值（它的参数），如果字符串成功显示则返回`true`，否则返回`false`。
 - `print_r()`: 可以把字符串和数字简单地打印出来，而数组则以括起来的键和值得列表形式显示，并以Array开头。**但`print_r()`输出布尔值和NULL的结果没有意义，因为都是打印"\n"。因此用`var_dump()`函数更适合调试。**
 - `var_dump()`: 判断一个变量的类型与长度,并输出变量的数值,如果变量有值输的是变量的值并回返数据类型。此函数显示关于一个或多个表达式的结构信息，包括表达式的类型与值。数组将递归展开值，通过缩进显示其结构。

### PHP EOF(heredoc) 使用说明

PHP EOF(heredoc)是一种在命令行shell（如sh、csh、ksh、bash、PowerShell和zsh）和程序语言（像Perl、PHP、Python和Ruby）里定义一个字符串的方法。

使用概述：

1. 必须后接分号，否则编译通不过。
2. EOF 可以用任意其它字符代替，只需保证结束标识与开始标识一致。
3. **结束标识必须顶格独自占一行(即必须从行首开始，前后不能衔接任何空白和字符)**。
4. 开始标识可以不带引号或带单双引号，不带引号与带双引号效果一致，解释内嵌的变量和转义符号，带单引号则不解释内嵌的变量和转义符号。
5. 当内容需要内嵌引号（单引号或双引号）时，不需要加转义符，本身对单双引号转义，此处相当与q和qq的用法。

示例：

``` php
<?php
echo <<<EOF
        <h1>我的第一个标题</h1>
        <p>我的第一个段落。</p>
EOF;
// 结束需要独立一行且前后不能空格
?>
```

注意：

 1. 以 <<<EOF 开始标记开始，以 EOF 结束标记结束，结束标记必须顶头写，不能有缩进和空格，且在结束标记末尾要有分号 。
 2. 开始标记和结束标记相同，比如常用大写的 EOT、EOD、EOF 来表示，但是不只限于那几个(也可以用：JSON、HTML等)，只要保证开始标记和结束标记不在正文中出现即可。
 3. 位于开始标记和结束标记之间的变量可以被正常解析，但是函数则不可以。在 heredoc 中，变量不需要用连接符 `.` 或 `,` 来拼接，如下：

``` php
<?php
$name="runoob";
$a= <<<EOF
        "abc"$name
        "123"
EOF;
// 结束需要独立一行且前后不能空格
echo $a;
?>
```
**总结**

 1. PHP 定界符 EOF 的作用就是按照原样，包括换行格式什么的，输出在其内部的东西；
 2. 在 PHP 定界符 EOF 中的任何特殊字符都不需要转义；
 3. PHP 定界符 EOF

EOF 中是不会解析 html 格式内容的，并且在双引号内的内容也有转义效果。

具体见下面例子:

``` php
<?php
$name="变量会被解析";
$a=<<<EOF
$name<br><p>html格式不会被解析</p><br/>双引号和Html格式外的其他内容都不会被解析
"双引号外所有被排列好的格式都会被保留"
"但是双引号内会保留转义符的转义效果,比如table:\t和换行：\n下一行"
EOF;
echo $a;
?>  
```
加不加引号转义字符都有效。

### 数据类型

> String（字符串）, Integer（整型）, Float（浮点型）, Boolean（布尔型）, Array（数组）, Object（对象）, NULL（空值）。

**字符串**

一个字符串是一串字符的序列，就像 "Hello world!"。

放在在单引号和双引号中的任何文本内容都叫字符串。

代码示例：

``` php
<?php
<?php 
echo "Hello world!";	//双引号包括
echo "<br>"; 
echo 'Hello world!';	//单引号包括
echo "<br>";
echo "H";	//单个字符
echo '<br>';
echo 'H';
?>

/*
输出内容：

Hello world!
Hello world!
H
H
*/
?>
```

**整型**

整数是一个没有小数的数字。

整数规则:

 - 整数必须至少有一个数字 (0-9)
 - 整数不能包含逗号或空格
 - 整数是没有小数点的
 - 整数可以是正数或负数
 - 整型可以用三种格式来指定：十进制， 十六进制（ 以 0x 为前缀）或八进制（前缀为 0）。
   
   

