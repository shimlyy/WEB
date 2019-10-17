background 的常见背景属性

css2.1 中，常见的背景属性有以下几种：（经常用到，要记住）

background-color:#ff99ff; 设置元素的背景颜色。

background-image:url(images/2.gif); 将图像设置为背景。

background-repeat: no-repeat; 设置背景图片是否重复及如何重复，默认平铺满。（重要）

no-repeat不要平铺；
repeat-x横向平铺；
repeat-y纵向平铺。
background-position:center top; 设置背景图片在当前容器中的位置。
background-attachment:scroll; 设置背景图片是否跟着滚动条一起移动。 属性值可以是：scroll（与fixed属性相反，默认属性）、fixed（背景就会被固定住，不会被滚动条滚走）。

另外还有一个综合属性叫做background，它的作用是：将上面的多个属性写在一个声明中。

CSS3 中，新增了一些background属性：

background-origin

background-clip 背景裁切

background-size 调整尺寸

多重背景

上面这几个属性经常用到，需要记住。现在我们逐个进行讲解。


background-color：背景颜色的表示方法

css2.1 中，背景颜色的表示方法有三种：单词、rgb表示法、十六进制表示法。

比如红色可以有下面的三种表示方法：

	background-color: red;
	background-color: rgb(255,0,0);
	background-color: #ff0000;
CSS3 中，有一种新的表示颜色的方式：RGBA或者HSLA。

RGBA、HSLA可应用于所有使用颜色的地方。

下面分别介绍。

用英语单词表示

能够用英语单词来表述的颜色，都是简单颜色。比如红色、绿色等。代码举例：

background-color: red;

RGB 表示法

RGB 表示三原色“红”red、“绿”green、“蓝”blue。

光学显示器中，每个像素都是由三原色的发光原件组成的，靠明亮度不同调成不同的颜色的。r、g、b的值，每个值的取值范围0~255，一共256个值。

比如红色：

background-color: rgb(255,0,0);
黑色：

background-color: rgb(0,0,0);
颜色可以叠加，比如黄色就是红色和绿色的叠加：

background-color: rgb(255,255,0);
RGBA 表示法

    background-color: rgba(0, 0, 255, 0.3);

    border: 30px solid rgba(0, 255, 0, 0.3);
解释：

RGBA 即：Red、Green、Blue、Alpha

R、G、B 的取值范围是：0~255


十六进制表示法

比如红色：

background-color: #ff0000;
PS:所有用#开头的值，都是16进制的。

这里，我们就要学会16进制与10进制之间的转换。下面举几个例子。

问：16进制中28等于10进制多少？ 答：2*16+8 = 40。

16进制中的af等于10进制多少？ 答：10 * 16 + 15 = 175

所以，#ff0000就等于rgb(255,0,0)。

background-color: #123456;等价于background-color: rgb(18,52,86);

十六进制可以简化为3位，所有#aabbcc的形式，能够简化为#abc。举例如下：

比如：

	background-color:#ff0000;
等价于：

	background-color:#f00;
比如：

	background-color:#112233;
等价于：

	background-color:#123;
但是，比如下面这个是无法简化的：

	background-color:#222333;
再比如，下面这个也是无法简化的：

	background-color:#123123;
几种常见的颜色简写可以记住。如下：

	#000   黑
	#fff   白
	#f00   红
	#222   深灰
	#333   灰
	#ccc   浅灰

HSLA 表示法

举例：

	background-color: hsla(240,50%,50%,0.4);
解释：

H 色调，取值范围 0~360。0或360表示红色、120表示绿色、240表示蓝色。

S 饱和度，取值范围 0%~100%。值越大，越鲜艳。

L 亮度，取值范围 0%~100%。亮度最大时为白色，最小时为黑色。

A 透明度，取值范围 0~1。
推荐链接：配色宝典 http://www.uisdc.com/how-to-create-color-palettes

关于设置透明度的其他方式：

（1）opacity: 0.3; 会将整个盒子及子盒子设置透明度。也就是说，当盒子设置半透明的时候，会影响里面的子盒子。

（2）background: transparent; 可以单独设置透明度，但设置的是完全透明（不可调节透明度）。


background-position属性

background-position属性指的是背景定位属性。公式如下：

在描述属性值的时候，有两种方式：用像素描述、用单词描述。下面分别介绍。

1、用像素值描述属性值：

格式如下：

	background-position:向右偏移量 向下偏移量;
属性值可以是正数，也可以是负数。比如：100px 200px、-50px -120px。


2、用单词描述属性值：

格式如下：

	background-position: 描述左右的词 描述上下的词;
描述左右的词：left、center、right
描述上下的词：top 、center、bottom
比如说，right center表示将图片放到右边的中间；center center表示将图片放到正中间。

比如说，bottom表示图片的底边和父亲底边贴齐（好好理解）。

场景2：（通栏banner）

很多网站的首页都会有banner图（网站最上方的全屏大图叫做「通栏banner」），这种图要求横向的宽度特别大。比如说，设计师给你一张1920*465的超大banner图，如果我们把这个banner图作为img标签直接插入网页中，会有问题的：首先，图片不在网页的中间；其次，肯定会出现横向滚动条。
正确的做法是，将banner图作为div的背景图，这样的话，背景图超出div的部分，会自动移溢出。需要给div设置的属性如下：

        div{
            height: 465px;
            background-image: url(http://img.smyhvae.com/20170813_1053.jpg);
            background-position: center top;
            background-repeat: no-repeat;
        }
上方代码中，我们给div设置height（高度为banner图的高度），不需要设置宽度（因为宽度会自动霸占整行）。


background-attachment 属性

background-attachment:scroll; 设置背景图片是否固定。属性值可以是：
fixed（背景就会被固定住，不会被滚动条滚走）。
scroll（与fixed属性相反，默认属性）
background-attachment:fixed;的效果如下：


background 综合属性

background属性和border一样，是一个综合属性，可以将多个属性写在一起。(在盒子模型这篇文章中专门讲到border)

举例1:

	background:red url(1.jpg) no-repeat 100px 100px fixed;
等价于：

	background-color:red;
	background-image:url(1.jpg);
	background-repeat:no-repeat;
	background-position:100px 100px;
	background-attachment:fixed;
以后，我们可以用小属性层叠掉大属性。

上面的属性中，可以任意省略其中的一部分。

比如说，对于下面这样的属性：

	background: blue url(images/wuyifan.jpg) no-repeat 100px 100px;

background-size属性：背景尺寸

background-size属性：设置背景图片的尺寸。

格式举例：

	/* 宽、高的具体数值 */
	background-size: 500px 500px;

	/* 宽高的百分比（相对于容器的大小） */
	background-size: 50% 50%;   // 如果两个属性值相同，可以简写成：background-size: 50%;

	background-size: 100% auto;  //这个属性可以自己试验一下。

	/* cover：图片始终填充满容器，且保证长宽比不变。图片如果有超出部分，则超出部分会被隐藏。 */
	background-size: cover;

	/* contain：将图片完整地显示在容器中，且保证长宽比不变。可能会导致容器的部分区域为空白。  */
	background-size: contain;
  
  这里我们对属性值 cover 和 contain 进行再次强调：

cover：图片始终填充满容器，且保证长宽比不变。图片如果有超出部分，则超出部分会被隐藏。

contain：将图片完整地显示在容器中，且保证长宽比不变。可能会导致容器的部分区域留白。

代码举例：（这张图片本身的尺寸是 1080 * 1350）

背景原点：background-origin 属性

background-origin 属性：控制背景从什么地方开始显示。

格式举例：

	/* 从 padding-box 内边距开始显示背景图 */
	background-origin: padding-box;           //默认值

	/* 从 border-box 边框开始显示背景图  */
	background-origin: border-box;

	/* 从 content-box 内容区域开始显示背景图  */
	background-origin: content-box;
如果属性值设置成了border-box，那边框部分也会显示图片哦。








