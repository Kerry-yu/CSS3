## 一、如何学习CSS

+ CSS快速入门
  1. CSS选择器（重点+难点）
  2. 美化网页（文字，阴影，超链接，列表，渐变……）
  3. 盒子模型
  4. 浮动
  5. 定位
  6. 网页动画

## 二、CSS简单介绍

### 1.  什么是CSS

> Cascading Style Sheet	层叠级联样式表

1. CSS：表现（美化网页）

   字体、颜色、边距、高度、宽度、背景图片、网页定位、网页浮动

2. CSS优势：

   1. 内容和表现分离
   2. 网页结构表现统一，可以实现复用
   3. 样式十分的丰富
   4. 建议使用独立于html的css文件
   5. 利于SEO，容易被搜索引擎收录



### 2. CSS发展史

+ CSS1.0
+ CSS2.0：div(块) + CSS，HTML与CSS结构分离的思想，网页变得简单，利用SEO
+ CSS2.1：浮动，定位
+ CSS3.0：圆角，阴影，动画…… 

### 3. 快速入门

1. 在html文件中编写css代码——**style标签**

   ~~~html
   <head> 
   <!--
   	规范，<style> 可以编写css的代码
   	语法：
   		选择器{
   			声明1;
   			声明2;
   			声明3;
   			}
   -->
   	<style>
   		h1{
   			color:red;
   		}
   	</style>
   </head>
   
   <body>
   	<h1>我是标题</h1>
   </body>
   ~~~

2. css和html文件分离（建议使用）

   css代码放入css文件，html使用**link标签**引用

   CSS：

   ~~~css
   h1{
       color:red;
   }
   ~~~

   HTML：

   ~~~html
   <head>    
       <link rel="stylesheet" href="/1.css/css/style.css">
   </head>
   ~~~

   ![image-20210728145447941](https://img.wkeyu.cn/blog/paper/20210803155012.png)

### 4. CSS的三种导入方式

#### 4.1 行内样式

~~~html
<body>
<!--行内样式：在标签元素中，编写一个style属性，编写样式即可-->
<h1 style="color: red;">标题一</h1>    
</body>
~~~

#### 4.2 内部样式

~~~html
<head>
<!--内部样式-->
	<style>
		h1{
			color: green;
		}   
</head>
~~~

#### 4.3 外部样式（**样式在css文件中，html需要link标签**）

~~~css
/* 外部样式 */
h1{
    color: yellow;
}
~~~

+ 优先级顺序

  ==**就近原则**==，谁离h1更近，css属性是谁

+ 拓展：外部样式两种写法：

  + 链接式	link
  + 导入式    @import url 

## 三、CSS选择器

+ 作用：选择页面上的某一个或某一类元素

### 1. 基本选择器

#### 1.1 标签选择器：

选择一类标签

~~~html
<head>
<style>
/* 标签选择器会选择到这个页面上所有的该类标签 */
	h1{
		color: green;
		background-color: hotpink;
		border-radius: 24px;
	}
	p{
		font-size: 80px;
	}
</style>
</head>

<body>
<h1>标题一</h1>
<h1>二号标题一</h1>
<p>啦啦啦</p>
</body>
~~~

![image-20210728170201510](https://img.wkeyu.cn/blog/paper/20210803155033.png)

#### 1.2 类选择器

 选择所有class属性一致的标签，类可以复用

~~~html
<head>
	<style>
	/* 类选择器的格式 .class的名称{} */
		.kerry{
			color: red;
			}
		.korry{
			color: green;
			}
	</style>
</head>

<body>
	<h1 class="kerry">标题一</h1>
	<h1 class="korry">标题二</h1>
    <h1 class="kerry">标题三</h1>
	<h1 class="korry">标题四</h1>

</body>
~~~

![image-20210728173951478](https://img.wkeyu.cn/blog/paper/20210803155042.png)

#### 1.3 id选择器

id全局唯一！

~~~html
<head>
    <style>
	/* 
		id选择器: id必须保证全局唯一
		#id名称{}
       优先级：id选择器> class选择器 >标签选择器
	*/
		#kerry{
            color: yellow;
        }
        #korry{
            color: red;
        }
    </style>
</head>

<body>
    <h1 id="kerry">标题1</h1>
    <h1 id="korry">标题2</h1>
    <h1>标题3</h1>
    <h1>标题4</h1>
</body>
~~~

![image-20210728174231491](https://img.wkeyu.cn/blog/paper/20210803155048.png)

> **优先级：id选择器>class 选择器> 标签选择器**



### 2. 层次选择器

+ 网站框架：

  ![image-20210729095330738](https://img.wkeyu.cn/blog/paper/20210803155052.png)

+ html代码：

  ~~~html
  <body>
      <p>p1</p>
      <p class="mark">p2</p>
      <p>p3</p>
      <ul>
          <li>
              <p>p4</p>
          </li>
          <li>
              <p>p5</p>
          </li>
          <li>
              <p>p6</p>
          </li>
      </ul>
      <p>p7</p>
  </body>
  ~~~

  ![image-20210729095942472](https://img.wkeyu.cn/blog/paper/20210803155055.png)

#### 2.1 后代选择器

在某个元素后面的所有（如body后的p1-7）

~~~css
/* 后代选择器 */
body p {
    background-color: green;
}
~~~

![image-20210729100145174](https://img.wkeyu.cn/blog/paper/20210803155100.png)

#### 2.2 子选择器

某个元素的下一代（如body后的p1-3，p7）`>`

~~~css
/* 子选择器 */
body>p{
    background-color: yellow;
}
~~~

![image-20210729100423529](https://img.wkeyu.cn/blog/paper/20210803155103.png)

#### 2.3 相邻弟弟选择器

当前选中元素的向下第一个弟弟元素

```css
 /* 相邻弟弟选择器 */
.mark + p{
		background-color: red;
	}
```

![image-20210729101132150](https://img.wkeyu.cn/blog/paper/20210803155107.png)

#### 2.4 通用选择器

当前选中元素的向下所有弟弟元素

~~~css
/* 通用弟弟选择器 */
.mark~p {
		background-color: blue;
	}
~~~

![image-20210729101257506](https://img.wkeyu.cn/blog/paper/20210803155111.png)

### 3. 结构伪类选择器

~~~html
<body>
    <p>p1</p>
    <p>p2</p>
    <p>p3</p>
    <ul>
        <li>li1</li>
        <li>li2</li>
        <li>li3</li>
    </ul>
    <p>p4</p>
</body>
~~~

~~~css
/* 选中ul的第一个子元素 */
ul li:first-child {
    background-color: blue;
}
/* 选中ul的最后一个子元素 */
ul li:last-child {
    background-color: orange;
}
/* 选中p1 ：定位到父元素，选择当前的第一个元素 */
p:nth-chile(1){
    background-color: red;
}
/* 选中父元素下的p元素的第二个 */
p:nth-of-type(2){
    background-color: green;
}
~~~

![image-20210730140039787](https://img.wkeyu.cn/blog/paper/20210803155118.png)

### 4. 属性选择器（常用）

初始条件：

网站html代码：

~~~html
<body>
    <p class="demo"></p>
    <a href="https://wwww.baidu.com" class="links item first" id="first">1</a>
    <a href="" class="links item active" target="_blank" title="test">2</a>
    <a href="images/123.html" class="links item" id="third">3</a>
    <a href="images/123.png" class="links item">4</a>
    <a href="images/123.jpg">5</a>
    <a href="abc" class="links item">6</a>
    <a href="/a.pdf" class="links item">7</a>
    <a href="/abc.pdf" class="links item">8</a>
    <a href="abc.doc" class="links item">9</a>
    <a href="abcd.doc" class="links item last">10</a>
</body>
~~~

CSS代码：

~~~css
<style>
    .demo a {
		float: left;
		display: block;
		height: 50px;
		width: 50px;
		border-radius: 10px;
		background-color: pink;
		text-align: center;
		color: green;
		text-decoration-line: none;
		margin-right: 5px;
		font: bold 20px/50px Arial;
	}
</style>
~~~

![image-20210731155750387](https://img.wkeyu.cn/blog/paper/20210803155123.png)

---

> 属性名 = 属性值（正则表达式）
>
> = 	绝对等于
>
> *=	包含**
>
> ^=	以**开头
>
> $=	以**结尾

1. 选中id

   ~~~css
   /* 选中存在id的元素   a[]{}*/
   a[id] {
   	background-color: yellow;
   }
   
   a[id="third"] {
   	background-color: blue;
   }
   ~~~

   ![image-20210731160236911](https://img.wkeyu.cn/blog/paper/20210803155126.png)

2. 选择class中含有links的元素

   ~~~css
   /* 选中class中含有links的元素 */
   a[class*="links"] {
   	background-color: yellow;
   }
   ~~~

   ![image-20210731160741277](https://img.wkeyu.cn/blog/paper/20210803155132.png)

3. href中以http开头的元素

   ~~~css
   /* 选中href中以http开头的元素 */
   a[href ^= "http"]{
   	background-color: yellow;
   }
   ~~~

   ![image-20210731160956534](https://img.wkeyu.cn/blog/paper/20210803155135.png)

4. 以pdf结尾的元素

   ~~~css
   /* 选中以pdf结尾的元素 */
   a[href$="pdf"] {
   	background-color: yellow;
   }
   ~~~

   ![image-20210731161532406](https://img.wkeyu.cn/blog/paper/20210803155139.png)

## 四、美化网页元素

> span 标签
>
> div 标签

### 1. 字体样式—font

+ font-family：字体样
+ font-size：字体大小
+ font-weight：字体粗细
+ color：字体颜色

~~~html
<body>
    <h1>老虎</h1>
    <p class="p1">
        两个人在森林里，遇到了一只大老虎。A就赶紧从背后取下一双更轻便的运动鞋换上。B急死了，骂道：“你干嘛呢，再换鞋也跑可是老虎啊!”A说：“我只要跑得比你快就好了。”
    </p>

    <p>
        人生哲理：二十一世纪，没有危机感是最大的危机。异常是入关在即，电信，银行，保险，甚至是公务员这些我们以为十分稳定和有保障的企业，也会面临许多的变数。当更多的老虎来临时，我们有没有准备好自我的跑鞋
    </p>
</body>
~~~

~~~css
/* 
            font-family：字体样
            font-size：字体大小
            font-weight：字体粗细
            color：字体颜色
        */
body {
	font-family: 楷体;
    color: blue;
}
h1{
	font-size :50px; ;
}
.p1{
	font-weight: bold;
}
~~~

![image-20210731173613554](https://img.wkeyu.cn/blog/paper/20210803155143.png)

### 2.文本样式

+ color：颜色
+ text-align： center 居中 
+ text-indent：2em  首行缩进
+ 行高和块的高度一样,可以上下居中 : line-height = height
+ text-decoration: underline：下划线
+ text-decoration: line-through：中划线
+ text-decoration: overline：上划线

~~~html
<body>
    <h1>老虎</h1>
    <p class="p1">
        两个人在森林里，遇到了一只大老虎。A就赶紧从背后取下一双更轻便的运动鞋换上。B急死了，骂道：“你干嘛呢，再换鞋也跑可是老虎啊!”A说：“我只要跑得比你快就好了。”
    </p>

    <p class="p2">
        人生哲理：二十一世纪，没有危机感是最大的危机。异常是入关在即，电信，银行，保险，甚至是公务员这些我们以为十分稳定和有保障的企业，也会面临许多的变数。当更多的老虎来临时，我们有没有准备好自我的跑鞋
    </p>
</body>
~~~

~~~css
 /*
	color：颜色
	text-align：居中 
	text-indent：首行缩进
	行高和块的高度一样,可以上下居中	line-height=height
	text-decoration: underline：下划线
	text-decoration: line-through：中划线
	text-decoration: overline：上划线
*/
h1{
	color: pink;
	text-align: center;
	text-decoration: underline;
	text-decoration: line-through;
	text-decoration: overline;
}
.p1{
	text-indent: 2em;
}

.p2{
	height: 300px;
	line-height: 300px;
}
~~~

![image-20210802102839991](https://img.wkeyu.cn/blog/paper/20210803155146.png)

### 3. 超链接伪类

 **a**，**a：haver**

~~~html
<body>
    <a href="#">
        <img src="img/a.png" alt="su" />
    </a>
    <p>
        <a href="#">姓名：苏炳添</a>
    </p>
    <p id="grade">
        成绩：9.83
    </p>
</body>
~~~

~~~css
 /* 默认的颜色 */
a{
	text-decoration: none;
	color: black;
}
/* 鼠标悬浮的状态 */
a:hover{
	color: yellow;
	font-size: 30px;
}
/* 鼠标点击未释放的状态 */
a:active{
	color:green;
}
/* text-shadow: 阴影颜色,水平便宜,垂直偏移,阴影半径 */
#grade{
	text-shadow: skyblue 10px 10px ;
}
~~~

![image-20210802102743153](https://img.wkeyu.cn/blog/paper/20210803155150.png)

### 4. 列表样式

+ **list-style**

~~~html
<body>
    <div id="nav">
        <h2 class="title">全部商品分类</h2>
        <ul>
            <li>
                <a href="#">图书</a>
                <a href="#">音像</a>
                <a href="#">数字商品</a>
            </li>
            <li>
                <a href="#">家用电器</a>
                <a href="#">手机</a>
                <a href="#">数码</a>
            </li>
            <li>
                <a href="#">电脑</a>
                <a href="#">办公</a>
            </li>
            <li>
                <a href="#">家居</a>
                <a href="#">家装</a>
                <a href="#">厨具</a>
            </li>
            <li>
                <a href="#">服饰鞋帽</a>
                <a href="#">个护化妆</a>
            </li>
            <li>
                <a href="#">礼品箱包</a>
                <a href="#">钟表</a>
                <a href="#">珠宝</a>
            </li>
            <li>
                <a href="#">食品饮料</a>
                <a href="#">保健食品</a>
            </li>
            <li>
                <a href="#">彩票</a>
                <a href="#">旅行</a>
                <a href="#">充值</a>
                <a href="#">票务</a>
            </li>
        </ul>
    </div>
</body>
~~~

~~~css
#nav{
    width: 300px;
    background-color: gray;
}
.title{
    font-size: 18px;
    font-weight: bold;
    text-indent: 1em;
    line-height: 35px;
    background: red;
}
ul{
    background-color: gray;
}
ul li{
    height: 30px;
    list-style: none;
    text-indent: 1em;

}
a{
    text-decoration: none;
    font-size: 14px;
    color: black;
}
a:hover{
    color: yellow;
}
~~~

![image-20210802104730740](https://img.wkeyu.cn/blog/paper/20210803155153.png)

### 5. 背景

+ 背景颜色

+ 背景图片

  ~~~HTML
  <body>
      <h2 class="title">图片背景</h2>
      <div class="div1"></div>
      <div class="div2"></div>
      <div class="div3"></div>
  </body>
  ~~~

  ~~~CSS
  div {
      width: 1000px;
      height: 700px;
      border: 1px solid red;
      background-image: url(img/b.jpg); /*默认全部平铺*/
  }
  .title{
      /* 颜色,图片,图片位置,平铺方式 */
      background: red url(img/b.jpg) 270px 10px no-repeat;
  }
  .div1{
      background-repeat: repeat-x;
  }
  .div2{
      background-repeat: repeat-y;
  }
  .div3{
      background-repeat: no-repeat;
  }
  ~~~

+ 渐变


## 五、盒子模型

### 1. 什么是盒子

![image-20210803110402556](https://img.wkeyu.cn/blog/paper/20210803110414.png)

**margin：**外边距

**padding：**内边距

**border：**边框

### 2. 边框

边框的粗细 、样式 、颜色

~~~html
<body>
    <div id="box">
        <h2>会员登陆</h2>
        <form action="#">
            <div>
                <span>用户名：</span>
                <input type="text" />
            </div>
            <div>
                <span>密码：</span>
                <input type="text" />
            </div>
            <div>
                <span>邮箱：</span>
                <input type="text" />
            </div>
        </form>
    </div>
</body>
~~~

~~~css
/* 常用初始化 */
h2,u1,li,a,body {
    /* body总有一个默认的外边距是0 */
    margin: 0;
    padding: 0;
    text-decoration: none;
}

/* border:粗细，样式，颜色 */
#box {
    width: 300px;
    border-color: yellow;
}

h2{
    font-size: 16px;
    background-color: pink;
    line-height: 30px;
    color: powderblue;
}

form {
    background-color: tomato;
}

div div:nth-of-type(1) input {
    border: 3px solid black;
}
div div:nth-of-type(2) input {
    border: 3px dashed gray;
}
div div:nth-of-type(3) input {
    border: 2px solid brown;
}
~~~

![image-20210803160632540](https://img.wkeyu.cn/blog/paper/20210803160632.png)

### 3. 内外边距 

盒子的计算方式：你这个元素到底有多大？

margin+border+padding + 内容

外边距：上 右 下 左  顺时针顺序

~~~css
#box {
    width: 300px;
    border-color: yellow;
    /* 
        外边距：上 右 下 左  顺时针顺序
        margin:0;上下左右都为0
        margin:0 auto ;上下为0，左右为auto
        margin:0 1px 2px 3px
    */
    margin: 0 auto;
}
div:nth-of-type(1) {
    padding: 10px;
}
~~~

![image-20210803163008339](https://img.wkeyu.cn/blog/paper/20210803163008.png)

### 4.圆角边框

#### 4.1 圆角

边框： 左上 右上 右下 左下 顺时针方向

```html
<body>    <div></div></body>
```

~~~css
div{    width: 100px;    height: 100px;    border: 10px solid red;    /* 左上 右上 右下 左下 顺时针方向*/    border-radius: 50px 20px 10px 5px;}
~~~

![image-20210804094437626](https://img.wkeyu.cn/blog/paper/20210804094455.png)

#### 4.2 圆形

圆形：圆角边框=宽度

~~~css
/* 圆圈:圆角边框=宽度 */div {    width: 100px;    height: 100px;    border: 10px solid red;    border: radius 100px;}
~~~

![image-20210804094701178](https://img.wkeyu.cn/blog/paper/20210804094701.png)

#### 4.3 扇形样式

扇形：调整边框和边框的长宽

~~~css
#a {    width: 100px;    height: 50px;    border: 1px solid red;    border-radius: 50px 50px 0 0;}#b {    width: 50px;    height: 100px;    border: 1px solid red;    border-radius: 50px 0 0 50px;}
~~~

![image-20210804095449667](https://img.wkeyu.cn/blog/paper/20210804095449.png)

### 5. 盒子阴影

~~~css
div {    width: 100px;    height: 100px;    border: 10px solid red;    box-shadow: 10px 10px 10px yellow;}
~~~

![image-20210804100607726](https://img.wkeyu.cn/blog/paper/20210804100607.png)

## 六、浮动

### 1. 标准文档流

**文档流**指的是元素排版布局过程中，元素会**默认**自动从左往右，从上往下的**流式排列方式**。并最终窗体自上而下分成一行行，并在每行中从左至右的顺序排放元素。

块级元素：独占一行

~~~html
h1-h6	p	div		列表	……
~~~

行内元素：不独占一行

~~~html
span	a	img		strong	……
~~~

行内元素可以被包含在块级元素中；反之，则不可以

### 2. display

display:	inline:行内元素

  				 block:块元素
  	
  				 inline-block:是块元素,但是可以内联在一行
  	
  				 none

**实现行内元素排列的一种方式，但是我们很多情况都是使用float。**

~~~html
<body>
    <div>div块元素</div>
    <span>span行内元素</span>
</body>
~~~

~~~css
/* 
    inline:行内元素
    block:块元素
    inline-block:是块元素,但是可以内联在一行
    none
*/
div{
    width: 100px;
    height: 100px;
    border: 1px solid red;
    display: inline;
}
span{
    width: 100px;
    height: 100px;
    border: 1px solid red;
    display: inline-block;
}
~~~

![image-20210804104735859](https://img.wkeyu.cn/blog/paper/20210804104735.png)

### 3. float

左右浮动：float

浮动会脱离标准文档流，可能会造成父级边框塌陷。

~~~html
<body>
    <div id="father">
        <div class="layer01"><img src="../img/a.png" alt="" /></div>
        <div class="layer02"><img src="../img/b.jpg" alt="" /></div>
        <div class="lay03">
            滑动的盒子可以向左浮动,也可以向右浮动,直到它的边缘碰到或包含另一个浮动的盒子为止
        </div>
    </div>
</body>
~~~

~~~css
div {    margin: 10px;    padding: 5px;}#father {    border: 1px solid red;}.layer01 {    border: 1px solid #000;    /* display: inline-block; */    float: left;}.layer02 {    border: 1px solid #000;    /* display: inline-block; */    float: right;}
~~~

![image-20210804105940396](https://img.wkeyu.cn/blog/paper/20210804105940.png)

### 4. overflow

overflow添加侧边滑动

~~~html
<body>
    <div id="content">
        <img src="../img/a.png" alt="" />
        <p>
            今夕何夕兮，搴舟中流。 今日何日兮，得与王子同舟。 蒙羞被好兮，不訾诟耻。 心几烦而不绝兮，得知王子。 山有木兮木有枝，心悦君兮君不知。
        </p>
    </div>
</body>
~~~

~~~css
#content {
    width: 200px;
    height: 150px;
    overflow: scroll;
}
~~~

![image-20210804114256447](https://img.wkeyu.cn/blog/paper/20210804114256.png)

### 5. 父级边框塌陷问题

+ clear

  ~~~css
  clear:right 右侧不允许有浮动clear:left  左侧不允许有浮动clear:both  两侧不允许有浮动
  ~~~

解决方案：

1. 增加父级元素高度

2. 增加一个空div，清除浮动

   ~~~html
   <div class="clear"></div>
   ~~~

   ~~~css
   .clear{
   	clear:both;
   	margin:0;
   	padding:0;
   }
   ~~~

3. 在父级元素中增加overflow属性

   ~~~css
   #father {
       border: 1px solid red;
       overflow: hidden;
   }
   ~~~

4. 父类添加一个伪类 

   ~~~css
   #father:after{
       content: '';
       display: block;
       clear: both;
   }
   ~~~

![image-20210804114824796](https://img.wkeyu.cn/blog/paper/20210804114825.png)

-----

**小结：**

1. 浮动元素增加空div

   > 简单，但代码中尽量避免空div

2. 设置父元素的高度

   > 简单，但元素假设有了固定高度，就会被限制

3. overflow

   > 简单，下拉的一些场景避免使用

4. 父类添加一个伪类：after（推荐）

   > 不改变原有代码基础

## 七、定位

### 1. 相对定位

**相对定位：position： relative**

相对于原来的位置，进行指定的偏移；相对定位的话，仍然在标准文档流中，它原来的位置会被保留。



~~~html
<body>
    <div id="father">
        <div id="first">第一个盒子</div>
        <div id="second">第二个盒子</div>
        <div id="third">第三个盒子</div>
    </div>
</body>
~~~

~~~css
body {
    padding: 20px;
}

div {
    margin: 10px;
    padding: 5px;
    font-size: 12px;
    line-height: 25px;
}

#father {
    border: 1px solid red;
    padding: 0;
}

#first {
    background-color: yellowgreen;
    border: 1px solid orange;
    /* 相对定位:上下左右 */
    position: relative;
    top: -20px;
    left: 20px;
}

#second {
    background-color: tomato;
    border: 1px solid green;
}

#third {
    background-color: skyblue;
    border: 1px solid yellow;
}
~~~

![image-20210804144508511](https://img.wkeyu.cn/blog/paper/20210804144508.png)

-----

练习：

![image-20210804155559043](https://img.wkeyu.cn/blog/paper/20210804155559.png)

~~~html
<body>
    <div id="father">
        <div id="first">第一个盒子</div>
        <div id="second">第二个盒子</div>
        <div id="third">第三个盒子</div>
    </div>
</body>
~~~

~~~css
#father {
    width: 300px;
    height: 300px;
    border: 2px solid red;
    padding: 10px;
}

a {
    width: 100px;
    height: 100px;
    text-decoration: none;
    background-color: pink;
    line-height: 100px;
    text-align: center;
    color: white;
    display: block;
}

a:hover {
    background-color: skyblue;
}

.a2 {
    position: relative;
    right: -200px;
    top: -100px;
}

.a4 {
    position: relative;
    right: -200px;
    top: -100px;
}

.a5 {
    position: relative;
    right: -100px;
    top: -300px;
}
~~~

### 2. 绝对定位

**绝对定位：position： absolute**

1. 没有父级元素定位的情况下，相对于浏览器边框定位

2. 假设父级元素存在定位，我们通常会相对于父级元素进行定位

3. 在父级元素范围内移动

> 相对于父级或浏览器的位置，进行指定的偏移，绝对定位的话，它不在标准文档流中，原来的位置不会被保留

### 3. 固定定位

**固定定位：position： fixed**

~~~html
<body>
    <div>div1</div>
    <div>div2</div>
</body>
~~~

~~~css
body {
    height: 1000px;
}

div:nth-of-type(1) {
    width: 100px;
    height: 100px;
    background-color: red;
    position: absolute;
    right: 0;
    bottom: 0;
}

div:nth-of-type(2) {
    width: 50px;
    height: 50px;
    background-color: yellow;
    position: fixed;
    right: 0;
    bottom: 0;
}
~~~

![image-20210804161242093](https://img.wkeyu.cn/blog/paper/20210804161242.png)

### 4. z-index

网页图层优先级

z-index:最低是0；最高无限

## 八、总结



