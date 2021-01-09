* [PHP开发手册](#php开发手册)
	* [PHP基础知识](#php基础知识)
		* [介绍](#介绍)
		* [PHP 安装](#php-安装)
		* [PHP 语法](#php-语法)
		* [PHP变量](#php变量)
		* [PHP echo 和 print 语句](#php-echo-和-print-语句)
		* [PHP EOF(heredoc) 使用说明](#php-eofheredoc-使用说明)
		* [数据类型](#数据类型)
			* [String 字符串](#string-字符串)
			* [Integer 整型](#integer-整型)
			* [浮点型](#浮点型)
			* [数组](#数组)
			* [对象](#对象)
			* [NULL 值](#null-值)
		* [类型比较](#类型比较)
		* [PHP 5 常量](#php-5-常量)

	

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


> 语法解析时不同：
> 
>  - js 是查到 var 关键字, 然后将后面的字符定为指向那块内存的名称.
>  - php 是查到 $+变量名, 然后将 $+变量名 作为内存的名称.

·**创建（声明）PHP 变量**

当第一次给变量赋值的时候才创建变量。

``` php
<?php
$x;	# 声明变量$x
x = 15;	# 这样赋值是错误的
$x = 15; # 必须这样赋值
echo $x;  // 15

// 只声明不赋值
$y;
echo $y; // Notice: Undefined variable: x in C:\wamp64\www\test.php on line 3
?>

//定义变量（定义包括声明）
$z = 20;
echo $z;	//20
```

>  - php在不赋值只声明变量的情况下，不会设置默认值，而是会报错：Undefined variable。
>  - php的底层C是由一个联合体union来存储变量，这个联合体里面有各种变量类型，php都以long类型来存储整型，用hashtable哈西表来存储数组，因为union可以存储各种变量，并且解释器会自动判定变量类型，所以php不用声明变量类型，弱类型。
>  - $只是个语法糖，表示后面跟的是一个变量。

**PHP 是一门弱类型语言**

在上面的实例中，我们注意到，不必向 PHP 声明该变量的数据类型。

PHP 会根据变量的值，自动把变量转换为正确的数据类型。

php是弱类型语言，所以不需要声明变量类型即可使用。

在强类型的编程语言中，我们必须在使用变量前先声明（定义）变量的类型和名称。

如果按照内存空间分配来解释的话：

 - 弱类型的变量在分配内存空间时，这个内存空间可以存储任何类型的变量。使用的时候需要查找所有的内存区域
 - 强类型则按照变量类型分配在指定的内存中，不可直接转换类型。使用的时候直接去该类型的区域中找到该值。

所以一般在弱类型语言中改变变量类型可以直接修改。但是强类型语言不能直接修改，所以强类型语言的指针概念特别重要，我们不直接使用内存中的数据，我们创建一个引用型变量（指针），如果想修改的时候直接修改指针指向的内存地址就可以。

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

EOF 中是会解析 html 格式内容的，并且在双引号内的内容也有转义效果。

具体见下面例子:

``` php
<?php
$name="变量会被解析";
$a=<<<EOF
$name<br><a href="https://www.baidu.com">html格式不会被解析</a><br/>双引号和Html格式外的其他内容都不会被解析
"双引号外所有被排列好的格式都会被保留"
"但是双引号内会保留转义符的转义效果,比如table:\t和换行：\n下一行"
EOF;
echo $a;
?>   
```
加不加引号转义字符都有效。

### 数据类型

> String（字符串）, Integer（整型）, Float（浮点型）, Boolean（布尔型）, Array（数组）, Object（对象）, NULL（空值）。

#### String 字符串

一个字符串 string 就是由一系列的字符组成，其中每个字符等同于一个字节。这意味着 PHP 只能支持 256 的字符集，因此不支持 Unicode 。

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

> 注释：当您赋一个文本值给变量时，请记得给文本值加上单引号或者双引号。

**并置运算符**

在 PHP 中，只有这一个字符串运算符。

并置运算符 (.) 用于把两个字符串值连接起来。

代码示例：

``` php
<?php
$name = "grekevin";
$text = "最棒!";
echo $name . $text; 	//grekevin最棒!
echo "<br>";
echo $name . "你" . $text; 		//grekevin你最棒!
?>
```
**strlen() 函数**

strlen() 函数返回*字符串的长度（字节数）*。

``` php
<?php
$name = "grekevin";
$text = "最棒";
echo strlen($name);		//8
echo "<br>";
echo strlen($text);		//6 一个汉字3个字节
?>
```
**strpos() 函数**

strpos() 函数用于*在字符串内查找一个字符或一段指定的文本*。

如果在字符串中找到匹配，该函数会返回第一个匹配的字符位置。如果未找到匹配，则返回 FALSE。

示例代码：

``` php
<?php
$text = "hello grekevin";
echo strpos($text, "e"); 	//1 返回e在查找字符串中第一个出现的位置
echo "<br>";
echo strpos($text, "grekevin"); //6
?>
```

> 注意： 字符串中第一个字符的位置是 0，而不是 1





#### Integer 整型

integer 是集合 ℤ = {..., -2, -1, 0, 1, 2, ...} 中的某个数，是一个没有小数的数字。

整型值可以使用十进制，十六进制，八进制或二进制表示，前面可以加上可选的符号（- 或者 +）。

要使用八进制表达，数字前必须加上 0（零）。要使用十六进制表达，数字前必须加上 0x。要使用二进制表达，数字前必须加上 0b。

二进制表达的 integer 自 PHP 5.4.0 起可用。

> 从 PHP 7.4.0 开始，整型数值可能会包含下划线 (\_)，为了更好的阅读体验，这些下划线在展示的时候，会被 PHP 过滤掉。

整数规则:

 - 整数必须至少有一个数字 (0-9)
 - 整数不能包含逗号或空格
 - 整数是没有小数点的
 - 整数可以是正数或负数
 - 整型可以用三种格式来指定：十进制， 十六进制（ 以 0x 为前缀）或八进制（前缀为 0）。
   
 代码示例：
 
``` php
<?php
$a = 1234; // 十进制数
$a = 0123; // 八进制数 (等于十进制 83)
$a = 0x1A; // 十六进制数 (等于十进制 26)
$a = 0b11111111; // 二进制数字 (等于十进制 255)
$a = 1_234_567; // 整型数值 (PHP 7.4.0 以后)
?>
```

#### 浮点型

浮点数是带小数部分的数字，或是指数形式。

代码示例：

``` php
<?php 
$x = 10.365;
var_dump($x);
echo "<br>"; 
$x = 2.4e3;
var_dump($x);
echo "<br>"; 
$x = 8E-5;
var_dump($x);
?>   

/*
输出：
float(10.365)
float(2400)
float(8.0E-5)
*/
```

**Boolean 布尔类型**

布尔型可以是 `true` 或 `false`， 一般用于条件判断。

要指定一个布尔值，使用常量 true 或 false。两个都不区分大小写。

``` php
$x = true;	//设置 $x 的值为 TRUE
$y = false;	//设置 $y 的值为 FALSE
```

> 要明确地将一个值转换成 boolean，用 (bool) 或者 (boolean) 来强制转换。但是很多情况下不需要用强制转换，因为当运算符，函数或者流程控制结构需要一个 boolean 参数时，该值会被自动转换。

当转换为 boolean 时，以下值被认为是 false：

 - 布尔值 false 本身
 - 整型值 0（零）及 -0 (零)
 - 浮点型值 0.0（零）-0.0(零)
 - 空字符串，以及字符串 "0"
 - 不包括任何元素的数组
 - 特殊类型 NULL（包括尚未赋值的变量）
 - 从空标记生成的 SimpleXML 对象

所有其它值都被认为是 true（包括任何资源 和 NAN）。

> **警告**    -1 和其它非零值（不论正负）一样，被认为是 true！

#### 数组

数组可以在一个变量中存储多个值(同种类型或不同类型)。

代码示例：

``` php
<?php 
$names=array("Jim","Tom","Canot");	//同种类型的数据
echo "names:";
echo "<br>";
var_dump($names);

$ages = array(23, 15, "Tom");	//不同类型的数据
echo "ages:";
echo "<br>";
var_dump($ages);
?>

/*
环境：Wampserver64 + php7
输出:
names:
array (size=3)
  0 => string 'Jim' (length=3)
  1 => string 'Tom' (length=3)
  2 => string 'Canot' (length=5)
ages:
array (size=3)
  0 => int 23
  1 => int 15
  2 => string 'Tom' (length=3)
*/
```

#### 对象

对象数据类型也可以用于存储数据。

在 PHP 中，对象必须声明。

首先，你必须使用class关键字声明类对象。类是可以包含属性和方法的结构。

在类中定义数据类型，然后在实例化的类中使用数据类型：

代码示例：

``` php
<?php
class Car
{
    var $color;
    function __construct($color="green") {
      //关键字this就是指向当前对象实例的指针，不指向任何其他对象或类。
	  $this->color = $color;	
    }
    function what_color() {
      return $this->color;
    }
}

function print_vars($obj) {
   foreach (get_object_vars($obj) as $prop => $val) {
     echo "\t$prop = $val\n";
   }
}

// 实例一个对象
$herbie = new Car("white");

// 显示 herbie 属性
echo "herbie: Properties: ";
print_vars($herbie);
?>

/*
环境：Wampserver64 + php7
输出:
herbie: Properties: color = white
*/
```

#### NULL 值

NULL 值表示变量没有值。NULL 是数据类型为 NULL 的值，也是NULL类型唯一的值。

NULL 值指明一个变量是否为空值。 同样可用于数据空值和NULL值的区别。

可以通过设置变量值为 NULL 来清空变量数据：

``` php
<?php
$x="Hello world!";
$x=null;
var_dump($x);
?>

/*
输出：NULL
*/
```

### 类型比较

虽然 PHP 是弱类型语言，但也需要明白变量类型及它们的意义，因为我们经常需要对 PHP 变量进行比较，包含松散和严格比较。

 - 松散比较：使用两个等号 == 比较，只比较值，不比较类型。
 - 严格比较：用三个等号 === 比较，除了比较值，也比较类型。

示例代码：

``` php
<?php
if(42 == "42") {
    echo '值相等';
}
 
echo PHP_EOL; // 换行符
 
if(42 === "42") {
    echo '类型相等';
} else {
    echo '不相等';
}
?>

/*
输出：
值相等
不相等
*/
```

**PHP中 比较 0、false、null**

``` php
0 == false: bool(true)
0 === false: bool(false)

0 == null: bool(true)
0 === null: bool(false)

false == null: bool(true)
false === null: bool(false)

"0" == false: bool(true)
"0" === false: bool(false)

"0" == null: bool(false)
"0" === null: bool(false)

"" == false: bool(true)
"" === false: bool(false)

"" == null: bool(true)
"" === null: bool(false)
```

[多类型比较规则](https://www.php.net/manual/zh/language.operators.comparison.php)

[PHP类型比较表](https://www.php.net/manual/zh/types.comparisons.php)

### PHP 5 常量

常量是一个简单值的标识符，被定义后，在脚本的其他任何地方都不能改变常量的值。

一个常量由英文字母、下划线、和数字组成,但数字不能作为首字母出现。 (常量名不需要加 $ 修饰符)。

> **注意：** 常量在整个脚本中都可以使用。

设置常量，使用 define() 函数，函数语法如下：

> bool define ( string $name , mixed $value [, bool $case_insensitive = false ] )

该函数有三个参数:

 - name：必选参数，常量名称，即标志符。
 - value：必选参数，常量的值。
 - case_insensitive ：可选参数，如果设置为 TRUE，该常量则大小写不敏感。默认是大小写敏感的。

``` php
<?php
// 区分大小写的常量名
define("GREETING", "欢迎访问 Runoob.com");
echo GREETING;    // 输出 "欢迎访问 Runoob.com"
echo '<br>';
echo greeting;   // 输出 "greeting"

// 不区分大小写的常量名
define("GREETING", "欢迎访问 Runoob.com", true);
echo greeting;  // 输出 "欢迎访问 Runoob.com"
?>
```
使用常量时，不能在常量名前添加$ 符号，不然会将常量转换成新的未定义变量使用，会导致报错。

``` php
<?php
define('LOG','OPEN');//定义常量，常量使用不能添加$
echo $LOG;	//Notice: Undefined variable: LOG in C:\wamp64\www\test.php on line 3
?>
```
使用常量不能使用单引号或双引号：

``` php
<?php
define("NAME", "GREKEVIN");
echo NAME;	//GREKEVIN 
echo "<br>";

/*
使用常量不能在常量名上使用双引号或单引号
因为使用常量不能使用$，加上引号无法区分是字符串还是常量
*/

echo "NAME"; //NAME 
echo "<br>";
echo 'NAME'; //NAME
echo "<br>";
?>
```

**常量是全局的**

常量在定义后，默认是全局变量，可以在整个运行的脚本的任何地方使用。

``` php
<?php
define("NAME", "GREKEVIN");
echo NAME;	//GREKEVIN 

function test(){
	define("AGE", 16);
	echo NAME;	//GREKEVIN 函数内可以访问全局常量NAME
	echo "<br>";
	echo AGE;	//16	//访问局部常量AGE
}
echo "<br>";
// echo AGE;	//报错，函数内定义的常量，只能在函数局部作用域内访问到

test();
?>
```

