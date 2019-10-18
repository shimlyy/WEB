伪类（伪类选择器）
伪类：同一个标签，根据其不同的种状态，有不同的样式。这就叫做“伪类”。伪类用冒号来表示。

比如div是属于box类，这一点很明确，就是属于box类。但是a属于什么类？不明确。因为需要看用户点击前是什么状态，点击后是什么状态。所以，就叫做“伪类”。

静态伪类和动态伪类
伪类选择器分为两种。

（1）静态伪类：只能用于超链接的样式。如下：

:link 超链接点击之前
:visited 链接被访问过之后
PS：以上两种样式，只能用于超链接。

（2）动态伪类：针对所有标签都适用的样式。如下：

:hover “悬停”：鼠标放到标签上的时候
:active “激活”： 鼠标点击标签，但是不松手时。
:focus 是某个标签获得焦点时的样式（比如某个输入框获得焦点）
超链接a标签
超链接的四种状态
a标签有4种伪类（即对应四种状态），要求背诵。如下：

:link “链接”：超链接点击之前
:visited “访问过的”：链接被访问过之后
:hover “悬停”：鼠标放到标签上的时候
:active “激活”： 鼠标点击标签，但是不松手时。

对应的代码如下：

<style type="text/css">
	/*让超链接点击之前是红色*/
	a:link{
		color:red;
	}

	/*让超链接点击之后是绿色*/
	a:visited{
		color:orange;
	}

	/*鼠标悬停，放到标签上的时候*/
	a:hover{
		color:green;
	}

	/*鼠标点击链接，但是不松手的时候*/
	a:active{
		color:black;

</style>
记住，在css中，这四种状态必须按照固定的顺序写：

a:link 、a:visited 、a:hover 、a:active

超链接的美化
问：既然a{}定义了超链的属性，和a:link{}定义了超链点击之前的属性，那这两个有啥区别呢？

答：

a{}和a:link{}的区别：

a{}定义的样式针对所有的超链接(包括锚点)
a:link{}定义的样式针对所有写了href属性的超链接(不包括锚点)
超链接a标签在使用的时候，比较难。因为不仅仅要控制a这个盒子，也要控制它的伪类。

我们一定要将a标签写在前面，将:link、:visited、:hover、:active这些伪类写在后面。

针对超链接，我们来举个例子：

为了实现上面这个效果，完整版代码如下：

<!DOCTYPE html PUBLIC "-//W3C//DTD XHTML 1.0 Transitional//EN" "http://www.w3.org/TR/xhtml1/DTD/xhtml1-transitional.dtd">
<html xmlns="http://www.w3.org/1999/xhtml" xml:lang="en">
<head>
	<meta http-equiv="Content-Type" content="text/html;charset=UTF-8">
	<title>Document</title>
	<style type="text/css">
		*{
			margin: 0;
			padding: 0;
		}
		.nav{
			width: 960px;
			height: 50px;
			border: 1px solid red;
			margin: 100px auto;
		}
		.nav ul{
			/*去掉小圆点*/
			list-style: none;
		}
		.nav ul li{
			float: left;
			width: 120px;
			height: 50px;
			/*让内容水平居中*/
			text-align: center;
			/*让行高等于nav的高度，就可以保证内容垂直居中*/
			line-height: 50px;
		}
		.nav ul li a{
			display: block;
			width: 120px;
			height: 50px;
		}
		/*两个伪类的属性，可以用逗号隔开*/
		.nav ul li a:link , .nav ul li a:visited{
			text-decoration: none;
			background-color: purple;
			color:white;
		}
		.nav ul li a:hover{
			background-color: orange;
		}
	</style>
</head>
<body>
	<div class="nav">
		<ul>
			<li><a href="#">网站栏目</a></li>
			<li><a href="#">网站栏目</a></li>
			<li><a href="#">网站栏目</a></li>
			<li><a href="#">网站栏目</a></li>
			<li><a href="#">网站栏目</a></li>
			<li><a href="#">网站栏目</a></li>
			<li><a href="#">网站栏目</a></li>
			<li><a href="#">网站栏目</a></li>
		</ul>
	</div>
</body>
</html>

上方代码中，我们发现，当我们在定义a:link和 a:visited这两个伪类的时候，如果它们的属性相同，我们其实可以写在一起，用逗号隔开就好，摘抄如下：

		.nav ul li a{
			display: block;
			width: 120px;
			height: 50px;
		}
		/*两个伪类的属性，可以用逗号隔开*/
		.nav ul li a:link , .nav ul li a:visited{
			text-decoration: none;
			background-color: purple;
			color:white;
		}
		.nav ul li a:hover{
			background-color: orange;
		}
    
    如上方代码所示，最标准的写法，就是把link、visited、hover这三个伪类都要写。但是前端开发工程师在大量的实践中，发现不写link、visited也挺兼容。写法是：

a:link、a:visited都是可以省略的，简写在a标签里面。也就是说，a标签涵盖了link、visited的状态（前提是都具有了相同的属性）。写法如下：

		.nav ul li a{
			display: block;
			width: 120px;
			height: 50px;
			text-decoration: none;
			background-color: purple;
			color:white;
		}
		.nav ul li a:hover{
			background-color: orange;
		}
当然了，在写a:link、a:visited这两个伪类的时候，要么同时写，要么同时不写。如果只写a属性和a:link属性，不规范。
