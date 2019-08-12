## ***Sass***知识点

### 导入(Import)

被用来导入的文件的文件名前要添加下划线，如以下格式：

```
// _common.scss、_variables.scss
```



而在需要导入文件时，会使用到引入方法，所引入文件不需要写下划线，以上面文件为例：

```
// 利用@import导入文件
@import 'variables';
@import 'common';
```



### 变量(Variables)

在***Sass***中，声明变量的方式是使用***“$”***符号，具体方法为：

```scss
/*-------
_variables.scss
-------*/
// 定义背景色
$background-color: #fff;
// 定义头部颜色
$header-color: #eee;
```



在使用变量时，同样是使用***“$”***符号，前提是已经引入变量文件或者变量是在同一文件中定义：

```scss
/*-------
style.scss
-------*/
@import "variables";
body {
	background: $background-color;
}
header {
	background: $header-color;
}
```



### 嵌套(Nesting)

在***Sass***中，可以使用嵌套书写的方式编写样式，减少重复冗余工作。

```scss
.header {
	background: $header-color;
	// 等同于 ".header .title"
	.title {
		font-size: 18px;
		// 等同于 ".header .title h2"
		h2 {
			color: #eee;
			font-weight: bold;
		}
	}
	// 等同于 ".header a"
	a {
		text-decoration: none;
	}
}
```



### 混入(Mixins)

在***Sass***中，我们可以使用定义函数的方式编写样式，这种定义函数的方式，就是混入。

在***Sass***文件中，我们使用***"@mixin"***的方式定义函数：

```scss
@mixin transform($property) {
	-webkit-transform: $property;
	-ms-transform: $property;
	transform: $property;
}
```



在***Sass***文件中，我们使用***"@include"***的方式引入函数：

```scss
.title {
	@include transform(rotate(-10deg));
}
```



### 继承(Extend/Inheritance)

在使用***Sass***时，我们可以先定义一些父类样式，在后续开发过程中我们可以使用继承父类的方式，提高开发效率。

在***Sass***中我们使用***"%"***符号定义父类：

```scss
%title-style {
	font-size: 24px;
	line-height: 30px;
	font-weight: bold;
}
```



在后续使用***"@extend"***实现继承父类样式：

```scss
header {
	h2 {
		@extend %title-style;
	}
}
```



### 运算符(Operators)

在***Sass***中我们能直接使用四则运算符进行运算，方便快捷，简化开发：

```scss
.container {
	width: 100%;
}

article[role="main"] {
	float: left;
	width: 600px / 960px * 100%;
}

aside[role="complementary"] {
	float: right;
	width: 300px / 960px * 100%;
}
```



