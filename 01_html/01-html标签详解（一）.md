1、常见的几种 meta 标签如下：

（1）字符集 charset：

<meta http-equiv="Content-Type" content="text/html;charset=UTF-8">
字符集用meta标签中的charset定义，meta表示“元”。“元”配置，就是表示基本的配置项目。

charset就是charactor set（即“字符集”）。

浏览器就是通过meta来看网页是什么字符集的。比如你保存的时候，meta写的和声明的不匹配，那么浏览器就是乱码。

（2）视口 viewport：

    <meta name="viewport" content="width=device-width, initial-scale=1.0">
width=device-width ：表示视口宽度等于屏幕宽度。

viewport 这个知识点，初学者还比较难理解，以后学 Web 移动端的时候会用到。

（2）定义“关键词”：

举例如下：

<meta name="Keywords" content="网易,邮箱,游戏,新闻,体育,娱乐,女性,亚运,论坛,短信" />
这些关键词，就是告诉搜索引擎，这个网页是干嘛的，能够提高搜索命中率。让别人能够找到你，搜索到你。

（3）定义“页面描述”：

meta除了可以设置字符集，还可以设置关键字和页面描述。

只要设置Description页面描述，那么百度搜索结果，就能够显示这些语句，这个技术叫做SEO（search engine optimization，搜索引擎优化）。
title 标签:

用于设置网页标题：

	<title>网页的标题</title>
title也是有助于SEO搜索引擎优化的。

base标签：

<base href="/">
base 标签用于指定基础的路径。指定之后，所有的 a 链接都是以这个路径为基准。

２、<body>标签的属性
    
其属性有：

bgcolor：设置整个网页的背景颜色。
background：设置整个网页的背景图片。
text：设置网页中的文本颜色。
leftmargin：网页的左边距。IE浏览器默认是8个像素。
topmargin：网页的上边距。
rightmargin：网页的右边距。
bottommargin：网页的下边距。
link属性表示默认显示的颜色、alink属性表示鼠标点击但是还没有松开时的颜色、vlink属性表示点击完成之后显示的颜色。

3、块级标签 <div>和<span>
<span>和<div>唯一的区别在于：<span>是不换行的，而<div>是换行的。
 
4，预定义（预格式化）标签：<pre>
含义：将保留其中的所有的空白字符(空格、换行符)，原封不动的输出结果（告诉浏览器不要忽略空格和空行） 说明：真正排网页过程中，<pre>标签几乎用不着。但在PHP中用于打印一个数组时使用。

5，特殊字符（转义字符）
&nbsp;：空格 （non-breaking spacing，不断打空格）
&lt;：小于号（less than）
&gt;：大于号（greater than）
&amp;：符号&
&quot;：双引号
&apos;：单引号
&copy;：版权©
&trade;：商标™
&#32464;：文字绐。其实，#32464是汉字绐的unicode编码。

特殊字符	描述	字符的代码
空格符	&nbsp;
<	小于号	&lt;
> 	大于号	&gt;
&	和号	&amp;
￥	人民币	&yen;
©	版权	&copy;
®	注册商标	&reg;
°	摄氏度	&deg;
±	正负号	&plusmn;
×	乘号	&times;
÷	除号	&divide;
²	平方2（上标2）	&sup2;
³	立方3（上标3）	&sup3;

<u>：下划线标记

<s>或<del>：中划线标记（删除线）

<i>或<em>：斜体标记

6，超链接的属性
href：目标URL
title：悬停文本。
name：主要用于设置一个锚点的名称。
target：告诉浏览器用什么方式来打开目标页面。target属性有以下几个值：
_self：在同一个网页中显示（默认值）
_blank：在新的窗口中打开。
_parent：在父窗口中显示
_top：在顶级窗口中显示

7，img标签的其他属性
width：宽度

height：高度

Align：指图片的水平对齐方式，属性值可以是：left、center、right

title：提示性文本。公有属性。也就是鼠标悬停时出现的文本。

border：给图片加边框（描边），单位是像素，边框的颜色是黑色

Hspace：指图片左右的边距

Vspace：指图片上下的边距

alt：当图片不可用（无法显示）的时候，代替图片显示的内容。alt是英语 alternate “替代”的意思，代表替换资源。（有的浏览器不支持）
注意事项： （1）如果要想保证图片等比例缩放，请只设置width和height中其中一个。 （2）如果想实现图文混排的效果，请使用align属性，取值为left或right。
