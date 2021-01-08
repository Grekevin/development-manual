* [PHP开发手册](#php开发手册)
	* [PHP基础知识](#php基础知识)
		* [介绍](#介绍)
		* [PHP 安装](#php-安装)

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