# CSS基础

##  CSS初始

###  行内式（内联样式）

```html
<标签名 style="属性1:属性值1; 属性2:属性值2; 属性3:属性值3;"> 内容 </标签名>
```

### 内部样式表（内嵌样式表）

```html
<head>
<style type="text/CSS">
    选择器 { 
      属性1:属性值1;
      属性2:属性值2; 
      属性3:属性值3;
    }
</style>
</head>
```

​	style标签一般位于head标签中title标签之后，也可以把他放在HTML文档的任何地方type="text/css"  在

html5中可以省略。

### 外部样式表（外链式）

```html
<head>
  <link href="CSS文件的路径"  rel="stylesheet" />
</head>
```

注意：  link 是个单标签哦!!!

href：定义所链接外部样式表文件的URL，可以是相对路径，也可以是绝对路径

type：定义所链接文档的类型，在这里需要指定为“text/CSS”，表示链接的外部文件为CSS样式表。可以省略

rel：定义当前文档与被链接文档之间的关系，这里需要指定为“stylesheet”，表示被链接的文档是一个样式表文件

### 1.4 CSS初始团队约定

​	代码风格: 
​			紧凑格式
​			展开格式

​	代码大小写: 
​			样式选择器，属性名，属性值关键字全部使用小写字母书写，属性字符串允许使用小写。

## CSS基础选择器

### 标签选择器（元素选择器）

```html
标签名{属性1:属性值1; 属性2:属性值2; 属性3:属性值3; }  或者
元素名{属性1:属性值1; 属性2:属性值2; 属性3:属性值3; }
```

###  类选择器(重点)

```html
	.类名  {   属性1:属性值1; 属性2:属性值2; 属性3:属性值3; }
```

###  id选择器

```html
	#id名 {属性1:属性值1; 属性2:属性值2; 属性3:属性值3; }
```

1. 需要调用 id="id名"

2. 同一个id选择器只能被调用一次,多次调用不符合w3c规范, js调用会出错

	3. 一个标签不能同时调用多个id选择器
	4. 一个标签可以同时调用类选择器和id选择器

###   通配符选择器

```
* { 属性1:属性值1; 属性2:属性值2; 属性3:属性值3; }
```

通配符选择器, 作用范围是页面上所有的标签, 影响页面的加载速度,不推荐使用

###  CSS基础选择器团队约定

​	尽量少用通用选择器 `*`

​	尽量不使用 ID 选择器

​	不使用无具体语义定义的标签选择器 div span 

##  CSS复合选择器

### 后代选择器

​	后代选择器 发生前提是嵌套关系

     		1. 父元素在前,子元素在后, 中间用空格隔开
     		2. 后代选择器可以无限制的隔代
     		3. 只要能代表父元素,子元素,后代选择器可以是任意选择器组合

### 子元素选择器

​	子代选择器, 父在前,子在后,用>连在一起, 选择的亲儿子, 可以是任意选择器的组合	

```css
.father > span {
			color: green;
			font-size: 100px;
		}
```

### 交集选择器

​	交集选择器, 满足2个条件,即是这个标签,同时又调用了后边的类(id)选择器,中间没有空格

```css
div.box {
			font-style: italic;
		}
```

### 并集选择器

​	并集选择器, 样式全部相同或者部分相同的选择器,通过逗号连在一起,进行集体的定义

​	注意: 并集选择器最后一个选择器没有逗号

### 相邻选择器

​	基本语法:  选择器1+选择器2,     目的是为了精准选择选择器1后边的选择器2

```css
div+p  是为了选择紧挨着div后边的p标签
```

## 伪类选择器(内植类)

```css
	:link      /* 未访问的链接 */
		超链接未访问的状态 :link省略不写
	:visited   /* 已访问的链接 */
		超链接访问之后的状态
	:hover     /* 鼠标移动到链接上 */
		鼠标悬停到超链接的状态
	:active    /* 选定的链接 */
		超链接激活的状态(鼠标按住超链接不松手)
```

## CSS样式属性

### CSS外观属性

#### 	 color:文本颜色		

```css
		1.预定义的颜色值，如red，green，blue等

		2.十六进制 #开头, 从0-9, a-f, 选6位

		3. rgb颜色表示法 rgb(a, b, c) 取值范围是0-255
```

#### 	text-indent:首行缩进

​			1em 就是一个字的宽度

#### 	 text-align:文本水平对齐方式

```css
		left：左对齐（默认值）

		right：右对齐		

		center：居中对齐(盒子里面的内容水平居中， 而不是让盒子居中对齐)
```

#### 	text-decoration 文本的装饰

```css
		none   默认，定义标准的文本， 取消下划线

		underline 下划线

		line-through 删除线

		overline 上划线
```

### CSS字体样式属性

#### 	 font-size:字号大小

​		多个字体用逗号隔开, 英文字体在前边, 中文字体写后边

​		em 相当于当前对象内文本的尺寸大小

​		px 像素，最常用，推荐使用

#### 	 font-family:字体

​		多个字体用逗号隔开, 英文字体在前边, 中文字体写后边	

```
		unicode 字体编码 :
			1.在页面上f12或者右键点击检查,调出开发者工具
			2.找到console(控制台)
			3.在控制台escape("中文字体的名称"),回车
			4.将%u替换为\,得到字体的unicode编码*/
```

​		

```
		常用技巧:
			现在网页中普遍使用14px+
			
			尽量使用偶数的数字字号。ie6等老式浏览器支持奇数会有bug
			
			各种字体之间必须使用英文状态下的逗号隔开
			
			中文字体需要加英文状态下的引号，英文字体一般不需要加引号。当需要设置英文字体时，英文字体名必须位于中文字体名之前
			
			如果字体名中包含空格、#、$等符号，则该字体必须加英文状态下的单引号或双引号
			例如font-family: "Times New Roman";
			
			尽量使用系统默认字体，保证在任何用户的浏览器中都能正确显示
```

​		

```
		常用字体:
			宋体   SimSun   \5B8B\4F53
			新宋体  NSimSun   \65B0\5B8B\4F53
			黑体  SimHei   \9ED1\4F53
			微软雅黑   Microsoft YaHei   \5FAE\8F6F\96C5\9ED1
			楷体-GB2312   KaiTi_GB2312   \6977\4F53_GB2312
			隶书   LiSu   \96B6\4E66
			幼圆   YouYuan   \5E7C\5706
			华文细黑   STXihei   \534E\6587\7EC6\9ED1
			细明体   MingLiU   \7EC6\660E\4F53
			新细明体   PMingLiU   \65B0\7EC6\660E\4F53
```

####  font-weight:字体粗细	

```
		数字 400 等价于 normal，而 700 等价于 bold
		normal 默认值 不加粗 等于400
		bold 加粗 等于700
```

#### font-style:字体风格

```
	normal 默认值  不倾斜
		italic  斜体
		oblique 倾斜
	letter-spacing 
		控制字(母)与字(母)之间的距离,值越大,间距越大,可以为负值
	word-spacing
		控制英文单词与单词之间的距离,对中文无效,值越大,间距越大,可以为负值
	line-height:行间距
		normal 默认值
```

```css
	font:综合设置字体样式 (重点)
		选择器{font: font-style  font-weight  font-size/line-height  font-family;}
		
		使用font属性时，必须按上面语法格式中的顺序书写，不能更换顺序，各个属性以空格隔开
		其中不需要设置的属性可以省略（取默认值），但必须保留font-size和font-family属性，否则font属性将不起作用
```

## CSS 三大特性

### CSS层叠性

​	当多个样式,作用于同一个(类)标签,发生了样式冲突,权重相同的时候,后边的样式会把前边的样式层叠掉

(覆盖掉),总是执行后边样式, 就近原则, 和样式调用顺序无关

### CSS继承性

​	子元素可以继承父元素的样式（text-，font-，line-这些元素开头的都可以继承，以及color属性） 文字类的样式

​	a标签不会继承父元素文字颜色

​	标题标签不会继承父元素的文字大小

### CSS优先级

​	权重计算公式
​			标签选择器 权重0,0,0,1
​			类选择器  权重 0,0,1,0
​			id选择器  权重 0,1,0,0
​			!important 权重 无穷大

​			标签选择器 < 类选择器  <  id选择器  <  行内样式  < !important
​			        0,0,0,1        0,0,1,0         0,1,0,0           1,0,0,0        无穷大

​	     如果子元素自身没有样式,会继承父元素的样式, 子元素的样式和父元素的样式发生冲突,永远执行子元素自身

的样式, 父元素继承的过来的样式,权重为0

​	如果样式(选择器)作用于子元素的父元素上,对于子元素来说,权重为0

​	如果样式(选择器)作用于子元素自己身上,权重会叠加

## CSS标签

### 标签的嵌套规范

​	1.块元素可以嵌套块元素、行内元素、行内块元素，div可以嵌套任意标签，p标签不能嵌套其他块元素，

​	    可以嵌套行内元素、行内块元素，不推荐标题里边嵌套其他块元素，可以嵌套行内元素、行内块元素

​	2.行内块不能嵌套块元素，可以嵌套行内元素、行内块元素

​	3.行内元素不能嵌套块元素、行内块元素，只能嵌套行内元素，a标签不能嵌套a标签

### 标签显示模式（display）

#### 块级元素(block-level)

​		典型代表：div, h1-h6, p, ul, ol, li, dl, dd, form等

​		1.独占一行

​		2.块元素不设置宽度的时候,默认父元素的宽度

​		3.块元素不设置高度的时候,默认高度为0, 内容会撑开高度

​		4.可以设置宽高

#### 行内元素(inline-level)

​		典型代表 a, span, strong, b, em, i, ins,u,del,s 

​		1.在一行上显示

​		2.行内元素不能设置宽高

  	  3.行内元素默认宽高0, 内容会撑开宽高

​		4.行内元素代码换行会生成缝隙

#### 行内块元素（inline-block）

​		典型代表 img, input, textarea, td 

​		1.在一行上显示

​		2.可以设置宽高

​		3.行内块元素代码换行会生成缝隙

#### 7.2.4 标签显示模式转换 display

​		块转行内：display:inline;

​		行内转块：display:block;

​		块、行内元素转换为行内块： display: inline-block;

## CSS 背景(background)

###  背景图片(image)

```css
	background-image : none | url (url) 
			none : 　无背景图（默认的）
			url : 　使用绝对或相对地址指定背景图像
```

### 背景颜色

```css
	background-color:color
			transparent 透明 默认值
```

###  背景平铺

```css
	background-repeat: no-repeat;
			repeat 默认值 沿x轴(水平方向),y轴(垂直方向)铺满盒子
			repeat-x 沿着水平方向平铺
			repeat-y 沿着垂直方向平铺
			no-repeat 不平铺
```

###  背景定位

```css
	background-position: 0 0;
			1.写方位值  left(左) | right(右) | center(居中)  | top(顶) | bottom(底)
				◆写2个方位值 没有顺序要求
				◆写1个方位值, 另外一个方位值默认center
			2.写具体的数值
				◆写2个数字, 第1个是距左边的距离,第2个距顶边的距离
				◆写1个数字, 另外值默认center
			3.方位值和数值混合使用
				◆如果第1个是方位值, 只能写水平方向 left | right | center
				◆如果第2个值方位值,只能写垂直方向 top | bottom | center
```

### 背景附着

```css
	background-attachment: fixed;
			scroll 默认值 背景图像会随着内容(滚动条)滚动
			fixed  固定   背景图像不会随着内容(滚动条)滚动
			如果背景附着的值为fixed的时候, 背景定位参考的不是盒子的大小,而是浏览器
```

###  背景属性连写

```css
	background:背景颜色 背景图片地址 背景平铺 背景滚动 背景位置
			   顺序尽量按照这个来,没有必须写的值, 如果不写,取默认值
```

## 行高

​	normal 默认值 约等于1.1-1.3

​	**一行文字,行高和盒子高度一致的时候,这行文字垂直居中**

​	一行文字,行高小于盒子高度的时候,这行文字偏上显示

​	一行文字,行高大于盒子高度的时候,这行文字偏下显示

##  盒子模型（Box Model）

### 外边距(margin)

```css
		margin-top:上外边距
		margin-right:右外边距
		margin-bottom:下外边距
		margin-left:左外边距

		margin:上外边距 右外边距  下外边距  左外边
```

### 外边距实现块元素居中

​		1.必须是块级元素

​		2.盒子必须指定了宽度（width）

​		3.然后就给左右的外边距都设置为auto，就可使块级元素水平居中

​		4.文字盒子居中图片和背景区别		

```css
			margin: 0 auto; 只能使设置了宽度的块元素水平居中
			text-align: center; 可以使块元素里边的文字,行内元素,行内块元素水平居中
			text-align: center; 可以使行内块元素里边的文字,行内元素,行内块元素水平居中
			text-align: center;  用在行内元素上无效
```

​		**5.行内元素只能设置左右的内外边距,不能设置上下的内外边距**

​		**6.外边距合并:**	

​					1.相邻块元素垂直外边距的合并
​								当上下相邻的两个块元素相遇时，如果上面的元素有下外边距margin-bottom，下面的元素有上外边距margin-top，

​						则他们之间的垂直间距不是margin-bottom与margin-top之和，而是两者中的较大者。这种现象被称为相邻块元素垂直外

​						边距的合并（也称`外边距塌陷`）

​				2.嵌套块元素垂直外边距的合并

​							1.对于两个嵌套关系的块元素，如果父元素没有上内边距及边框，则父元素的上外边距会与子元素的上外边距发生合

​						并，合并后的外边距为两者中的较大者，合并到父元素上,即使父元素的上外边距为0，也会发生合并

​							`2.解决方案:`

​							`可以为父元素定义1像素的上边框或上内边距`

​				     	`可以为父元素添加overflow:hidden。触发BFC, 块级格式化上下文, 独立的布局区域,不会受到外部因素的干扰` 

### 边框(border)

```css
		border : border-width || border-style || border-color 
		none：没有边框即忽略所有边框的宽度（默认值）
		solid：边框为单实线(最为常用的)
		dashed：边框为虚线  
		dotted：边框为点线
		double：边框为双实线
```

​		单边框连写, 线型为必写项

​		边框写法: 四条边框相同的连写, 线型为必写项

```css
		border: 2px solid red
```

​		四条边框不同的连写, 顺序是上右下左,顺时针

### 内边距(padding)

```css
		padding-top:上内边距
		padding-right:右内边距
		padding-bottom:下内边距
		padding-left:左内边距
```

```css
		内边距连写
			写1个值,代表上下左右内边距相同
			写2值, 第1个代表上下内边距, 第2个代表左右内边距
			写3个值, 第1个代表上内边距, 第2个值是左右内边距,第3个值下内边距
			写4个值,代表上右下左内边距,顺时针
```

```css
		padding不影响盒子宽度情况
			块元素不设置宽度的时候,给这个块元素设置左右的padding值,不会撑宽盒子，除了上边的特殊情况,其他的设置左右的padding			值都会撑宽盒子，高度不用考虑,只要设置上下的内边距,必然撑高盒子
			块元素不设置宽度的时候,默认的是父元素内容区域的宽度
```

### 内容区域(content)

​	1.内盒尺寸计算（元素实际大小）

​		盒子的实际的大小 =   内容区域的宽度或高度 +  内边距   +  边框

​	2.清除元素的默认内外边距

```css
	 	padding:0;         /* 清除内边距 */
		 margin:0;          /* 清除外边距 */
```

​	 3.盒子模型布局稳定性
​		 width >  padding  >   margin   

### 表格的细线边框

```css
	border-collapse:collapse; 表示相邻边框合并在一起
```

###  盒子阴影(CSS3)

```css
	box-shadow:水平阴影 垂直阴影 模糊距离（虚实）  阴影尺寸（影子大小）  阴影颜色  内/外阴影；
				第1个值是阴影的水平偏移量, 正值向右,负值向左
				第2个值是阴影的垂直偏移量, 正值向下,负值向上
				第3个值是阴影的模糊范围,没有负值
				第4个值是阴影的大小
				第5个值是阴影的颜色

		  内阴影:box-shadow: inset 0px 0px 100px 0 yellow
```

## 透明的设置(css3)

​	rgba() 控制单颜色的透明, a代表alpha,透明, 取值范围是0-1, 0.5的0可以省略掉

​	opacity 控制元素整体透明度,取值范围是0-1, 0.5的0可以省略掉

##  圆角边框(CSS3)

```css
	border-radius: 50%;
		1.四个圆角相同的做法
			border-radius: 50px
			border-top-left-radius: 50px 200px;
			border-top-right-radius: 150px;

		2.边框圆角连写, 和内外边距取值顺序一样
			border-radius: 40px;
			border-radius: 40px 100px;
			border-radius: 40px 100px 20px;
			border-radius: 40px 100px 20px 10px;
		3.椭圆切,用/连接,前边是水平半径,后边是垂直半径
			border-radius: 40px 100px 20px 10px / 100px 30px 80px 200px;
```



  1. 需要调用, 谁调用,谁生效,不调用,不生效, 调用class="类名"

  2. 多个标签可以同时调用一个类选择器

  3. 1个标签可以同时调用多个类选择器 class="类名 类名"

  4. 类选择器的命名规范:

     ​	1.不能以纯数字或者数字开头来定义类名

     ​	2.定义类名的时候,不能出现特殊字符(_ - 可以作为连接符)

     ​	3.不能使用中文来定义类名

## CSS布局

```css
	普通流
		一个网页内的标签元素按照**从上到下，从左到右**的顺序排列
			块级元素**会独占一行，**从上向下**顺序排列
			行内元素**会按照顺序，**从左到右**顺序排列
	浮动
	定位
```

###  浮动

​	指**设置了浮动属性的元素**会**脱离标准普通流的控制**，移动到其父元素中指定位置的过程

```css
	属性值
			none
			left
			right	
```

```css
	1.浮动的元素脱离标准流的控制, 不占据原来是位置
	2.浮动可以使(块)元素在一行上显示
	3.浮动只能浮动的到父元素的左边和右边, 会受到父元素内边距的约束
	4.浮动的元素顶对齐, 代码换行不会生成缝隙
	5.浮动的元素有了行内块的显示特点
		1.块元素浮动之后,不会默认父元素的宽度了,默认宽高为0, 内容会撑开宽高
		2.行内元素浮动之后可以设置宽高了
	6.浮动元素只会影响下边的元素,不会影响上边不浮动的标准流里边的块元素
	当文字,行内元素,行内块元素,遇到浮动元素不会跑到他的下边,会环绕浮动元素
```

###  清除浮动

​	清除浮动是为了解决父元素不能设置高度, 里边的浮动的子元素不能撑开父元素高度的问题

#### 额外标签法

​		就是在最后一个浮动元素的后边,添加额外标签,不推荐使用

```css
		<div style="clear:both;"></div> 
```

#### 父级添加overflow属性方法

```css
	给浮动元素的父元素(亲爹)使用overflow: hidden;清除浮动 ,触发了BFC,块级格式化上下文, 独立的布局区域
		overflow: hidden;
	弊端是如果子元素出了父元素的范围,会被隐藏掉
```

#### 使用after伪元素清除浮动	

```css
	给浮动元素的父元素(亲爹),调用.clearfix清除浮动
		.clearfix:after {
			content: '';
			display: block;
			height: 0;
			/*显示模式为隐藏*/
			visibility: hidden;
			clear: both;
		}
	/*为了兼容ie6-7清除浮动*/
		.cleafrix {
			*zoom: 1;
		}
```

####  使用before和after双伪元素清除浮动

​	给浮动元素的父元素(亲爹), 调clearfix 双伪元素清除

```css
		.clearfix:before, .clearfix:after {
			content: "";
			display: table;
		}
		.clearfix:after {
			clear: both;
		}
		/*兼容ie6-7清除浮动*/
		.clearfix {
			*zoom: 1;
		}
```

##  定位(position)

### 定位的概念

​		定位 = 定位模式 + 边偏移

### 边偏移	

```css
		top: top: 80px**顶端**偏移量，定义元素相对于其父元素**上边线的距离**
		bottom: bottom: 80px`**底部**偏移量，定义元素相对于其父元素**下边线的距离**。
		left: left: 80px**左侧**偏移量，定义元素相对于其父元素**左边线的距离**。
		right: right: 80px`**右侧**偏移量，定义元素相对于其父元素**右边线的距离。
```

```css
		注意：
		1. **边偏移**需要和**定位模式**联合使用，**单独使用无效**；
		2. `top` 和 `bottom` 不要同时使用；
		3. `left` 和 `right` 不要同时使用。
```

### 定位模式

#### 	静态定位	

```css
		不定位,不会动 标准流 元素默认的定位方式
		position: static;
```

#### 	相对定位

```css
		1.相对定位的元素不脱标,还占据原来的位置
		2.相对定位的元素位置偏移永远基于自身位置
		position: relative;
```

#### 	绝对定位

```css
		1.绝对定位的元素脱离了标准流的控制, 不占据原来的位置
		2.绝对定位的元素,如果所有的父元素都没有使用定位,位置偏移基于浏览器
		3.绝对定位的元素,如果父元素有定位,位置偏移基于离他最近的使用了定位的父元素位置偏移
		4.绝对定位的元素有了行内块的显示特点
		5.绝对定位的块元素,不会默认父元素的宽度了,默认宽高为0, 内容会撑开宽高
		6.绝对定位的行内元素可以设置宽高了

		position: absolute;

		7.绝对定位的盒子居中
		8.绝对定位**不能通过设置 `margin: auto` 设置**水平居中**

		绝对定位盒子居中的方法1：
			position: absolute;
			/*向右走父元素宽度的一半*/
			left: 50%;
			/*向左走盒子自身宽度的一半*/
			margin-left: -50px;
			/*向下走父元素高度的一半*/
			top: 50%;
			/*向上走盒子自身高度的一半*/
			margin-top: -50px;
			/*left: 0;*/
			/*bottom: 0;*/
			width: 100px;
			height: 100px;

		绝对定位盒子居中的方法2：
			/*这种方法子元素必须是设置的宽高,内容撑开的宽高无效*/
			left: 0;
			right: 0;
			top: 0;
			bottom: 0;
			margin: auto;
			width: 100px;
			height: 100px;
```

#### 固定定位	

```css
		浏览器
			1.固定定位的元素,脱离了标准流, 不占据原来的位置
			2.固定定位的元素位置偏移基于浏览器可视窗口
			3.固定定位的元素有了行内块元素的显示特点
				块元素不会默认父元素的宽度了,默认宽高0, 内容会撑开宽高
				行内元素可以设置宽高了
		position: fixed;
```

#### 子绝父相

​		1.子绝父相, 子元素绝对定位,父元素相对定位

​		2.父元素相对定位不脱标,在标准流占据位置

​		3.子元素绝对定位,可以移动到父元素的任意位置, 父元素占位置,下边盒子不能上来,布局正常

​		4.绝对定位基于浏览器和固定定位基于浏览器可视窗口的区别:

​			1.绝对定位的元素位置偏移基于浏览器的时候,会随着滚动条滚动

​			2.固定定位的元素位置偏移基于浏览器可视窗口,不会随着滚动条滚动

### 堆叠顺序（z-index）

​	 	1.属性值：正整数、负整数或 0，默认值是 0，数值越大，盒子越靠上

 		2.如果属性值相同，则按照书写顺序，后来居上；

​		 3. 数字后面不能加单位

​		 4. 只能应用于相对定位、绝对定位和固定定位的元素，其他标准流、浮动和静态定位无效

## CSS高阶技巧

### 元素的显示与隐藏

```css
		display: none; 隐藏对象,隐藏之后不占位置

		visibility 可见性
			visible : 　对象可视
			hidden : 　对象隐藏,隐藏之后还占位置

		overflow 溢出
			visible 溢出可见 默认值
			hidden 溢出隐藏
			scroll 不管内容是否溢出都生成滚动条
			auto 内容溢出生成滚动条,不溢出不生成滚动条,溢出的内容不占位置
```

###  CSS用户界面样式

#### 鼠标样式cursor

```css
		cursor:default 默认值 小白
		cursor:pointer 小手
		cursor:move  移动
		cursor:text  文本
		cursor:not-allowed  禁止
		cursor:help 帮助
```

#### 轮廓 outline		

```css
		清除轮廓线outline: none;
		清除轮廓线outline: 0;
```

#### 防止拖拽文本域resize

```css
		禁止文本域拖拽resize：none
```

###  溢出的文字隐藏

```css
		强制一行显示：white-space: nowrap;
		溢出隐藏：overflow: hidden;

		text-overflow : clip | ellipsis
		clip : 　不显示省略标记（...），而是简单的裁切 
		ellipsis : 　当对象内文本溢出时显示省略标记（...）

		想实现当行文本省略号效果：
			white-space: nowrap;
			overflow: hidden;
			text-overflow: ellipsis; 缺一不可
```

### vertical-align 行内块垂直对齐方式            

```css
		vertical-align : baseline |top |middle |bottom 
		baseline 基线对齐 默认值
		top 顶对齐
		middle 垂直居中
		bottom  底对齐

		控制行内元素,行内块元素,垂直对齐, 对块元素无效
		清除图片底部的缝隙, 就是将vertical-align的值,设置为除了baseline以外的值都可以,或者将图片转换为块元素,也可以实现清除		   图片底部缝隙
```

### CSS精灵技术（sprite）

​	1.测量需要的精灵图局部大小,给盒子设置成宽高

​	2. 背景定位的值,设置成测量的局部大小坐标值的负值		

### 结构伪类选择器(css3)

```css
	.father :first-child,选择父元素的第1个子元素
	.father :last-child, 选择父元素的最后一个子元素
	.father :nth-child(n) 选择父元素里边的第n个子元素
	.father :nth-last-child(n) 选择父元素里边的倒数第n个子元素
	.father :nth-of-type(n) 选择父元素里边同级相同的第n个子元素
```

### 占位符选择器(css3)

​		placeholder	占位符  输入内容的时候,占位符消失,删除文字之后,占位符显

```css
		input::placeholder {
			color: yellow;
		}
		占位符选择器, 设置占位符样式
```

### 属性选择器(css3)

#### 通过标签的属性来选择标签		

```css
		[href] {
			font-size: 40px;
			color: #f00;
		}
```

#### 通过完整的属性值来选择标签

```css
		[href="abc.html"] {
			font-size: 60px;
			color: #ccc;
		}
```

#### 通过属性值以某些字符开头来选择标签

```css
		[href^="a"] {
			font-size: 100px;
			color: pink;
		}
```

#### 通过属性值以某些字符结尾来选择标签

```css
		[href$="l"] {
			font-size: 50px;	
			color: purple;
		}
```

#### 通过属性值包含某些字符来选择标签

```css
		[href*="c"] {
			color: orange;
			font-size: 50px;
		}
```

### CSS盒模型

```css
	content-box
		默认值 标准盒模型, 盒子宽(高)=width(height)+padding值+边框粗细

	 border-box
		怪异盒模型  内边距和边框不会撑宽盒子
	 box-sizing: border-box
```

### 背景尺寸

```css
	cover
		背景图片等比例缩放, 填满盒子,背景图片有可能显示不完整
	contain
		背景图片等比例缩放, 显示完整,有可能填不满盒子
	写具体的数值
		写2个值,第1个代表宽,第2个代表高
		写1个值, 代表宽,高默认auto, 等比例缩放
	写百分比 参考的是盒子的百分比
		写2个值,第1个代表宽,第2个代表高
		写1个值, 代表宽,高默认auto, 等比例缩放
```

### 背景线性变化

```css
	背景线型渐变, 逗号隔开
		background-image: linear-gradient(to bottom, red, green);
```

### 多背景图片

​	多组背景图片逗号隔开, 设置背景颜色在最后一组,设置背景渐变在最后写

### 过渡

​	过渡是从一种状态到另外一种状态, 过渡需要触发条件, 通常过渡都是写在开始状态

```css
	transition: 1s;

	1.规定哪些属性需要过渡：
		all 默认值 全部属性过渡
			transition-property: all;
		多个属性过渡,用逗号隔开
	2.过渡的时间 默认值 0s 1s=1000ms
	3.过渡的运动曲线
		ease 默认值 逐渐慢下来
			transition-timing-function: ease;
		linear  均速
	4.过渡的延迟
		transition-delay: 1s
	5.过渡属性的连写, 时间为必写项,其他不写取默认值
		transition: all 1s linear 1s;
```

### 三角形的制作

​	三角形的制作,盒子宽高为0, 设置不同的边框颜色,得到三角形

​	写2个值,第1个代表上下边框粗细,第2个值代表左右边框粗细

```css
	.box {
			width: 0px;
			height: 0px;
			/*background-color: #ccc;*/
			border-style: solid;
			/*三角形的制作,盒子宽高为0, 设置不同的边框颜色,得到三角形*/
			border-color: red blue green transparent;
			/*写2个值,第1个代表上下边框粗细,第2个值代表左右边框粗细*/
			border-width: 10px 30px;
			margin: 0 auto;
		}
```

# CSS新属性

## 2D转换（transform）

### 位移

```css
		transform: translate(x,y);
		1.translate最多设置2个值，第一个值是水平，第二个值是垂直
		2.设置具体位置像素时，参照的是自己原有的位置
		3.translate若设置负值时，会实现逆方向移动
		4.若设置一个值时，只有水平方向有效
		5.可以设置百分比，百分比参照的是自身的大小
```

​			特点：若仅仅只是位移，盒子不会脱标。盒子原有的位置还在标准流中 

```css
		盒子居中解决方法1:
		position: absolute;
      	width: 100px;
     	height: 100px;
     	background: blue;
      	left: 0;
      	right: 0;
      	top:0;
      	bottom: 0;
      	margin: auto;

		盒子居中解决方法2:
		position: absolute;
      	width: 100px;
      	height: 100px;
      	background: blue;
      	left: 50%;
      	top: 50%;
      	margin-left: -50px;
      	margin-top: -50px;

		盒子居中解决方法3:
		position: absolute;
      	width: 199px;
      	height: 199px;
      	background: blue;
      	left: 50%;
      	top: 50%;
      	/* 位移 */
      	/* 优势：对于盒子不用计算向上或向左移动 */
      	transform: translate(-50%,-50%)
```

### 旋转

```css
		transform:rotate(角度)
			单位是deg
			负值，逆时针旋转
			正值，顺时针旋转

		旋转源点设置
		transform-origin: 水平 垂直;
			默认是按照中心点旋转的
			水平取值：left| center| right |像素
			垂直取值：top | center| bottom|像素
```

### 缩放

```css
		transform:scale(number,number) 
			最多设置2个值，第一个值表示缩放宽度，第二值表示高度。注意：不加单位
			放大：若大于1表示放大多少倍
			缩小：若设置的值大于0小于1表示缩小
			若设置一个值时，表示宽高一起缩放多少倍（等比例变化）
```

## 3D转换

### 3D介绍

​		近大远小

​		物体后面遮挡不可见

### 3维坐标系

​		x轴：水平向右      注意： x 右边是正值，左边是负值 

​		y轴：垂直向下      注意： y 下面是正值，上面是负值

​		z轴：垂直屏幕      注意： 往外面是正值，往里面是负值

### 位移

```css
		transform: translateX(100px)
			控制X轴 正值向右  负值向左
		transform: translateY(100px)
			控制Y轴 正值向下  负值向上
		transform: translateZ(100px)
			控制Z轴 正值向前-越来越大  负值向后-越来越小

		注意：若要设置多个轴时，不要分开设置，要在同一个transform中设置
              transform: translateX(100px) translateY(100px);
```

### 透视

​		1.透视我们也称为**视距**：视距就是人的眼睛到屏幕的距离

​		2.距离视觉点越近的在电脑平面成像越大，越远成像越小  

​		3.透视的单位是像素

​		4.目的：实现近大远小的效果
  5. 图解1：在tranlateZ值一样的情况下

     ​	（视距越大，物体越小）

     ​	（视距越小，物体越大）		 ![1567404968293](C:\Users\Administrator\AppData\Roaming\Typora\typora-user-images\1567404968293.png)

6.图解2：在视距一致的情况下
	translateZ值越大，则物体越大，translateZ值越小，则物体越小
	![1567405164484](C:\Users\Administrator\AppData\Roaming\Typora\typora-user-images\1567405164484.png)

7. perspective: 像素值
   	注意：透视要设置给父元素

### 旋转

```css
		transform: rotateX(角度)

		左手法则：
      			大拇指指向x的正值方向→右
      			其他手指弯曲的方向就是正值方向
```

```css
		transform: rotateY(角度)

		左手法则：
      			大拇指指向y的正值方向→下
      			其他手指弯曲的方向就是正值方向
```

```css
		transform: rotateZ(角度)
		顺时针：正值
```

​		**问题：若父盒子旋转或其他操作，则子盒子的立体效果不会保持**

​		解决方案：给父盒子设置 transform-style: preserve-3d;

## 动画

### 定义动画

```css
	@keyframes 动画序列名称 {
  		0%{
      		开始状态
  		}  
  		100%{
      		结束状态
  		}
	}
```

### 调用动画（播放电影）

```css
		animation-name	指定动画的名称

		animation-duration	指定动画持续的时长

		animation-timing-function	动画的运动曲线
			默认是 "ease" 缓冲
				  linear匀速
			  	  steps(数字)步长

		animation-delay	动画延迟

		animation-iteration-count	动画的次数
			默认是 1
				  infinite 无数次

		animation-direction		动画是否可以逆向播放
			默认是 "normal"
				  alternate逆播放

		animation-play-state	动画是否正在运行或暂停
			默认是 "running"
			  暂停 “paused”

		animation-fill-mode		动画是否保持结束后的状态
			保持 forwards 
			回到起始 backwards

		animation	所有动画属性的简写属性
		animation: 动画的名称 动画持续的时间（必写） 运动的曲线 延迟时间 动画的次数 是否可以逆播 是否					   保持结束状态; 

		steps(数字) 几步完成动画

				打印文字效果
				1. 文字是提前写好的
		 		2. 开始，文字看不到
				3. 在宽度变化中(动画中)，文字逐一看到

				轮播图
		 		1. 动画，动画的是内部盒子ul
				2. 动画变化的是ul的横向x位置 
		 		3. 开始位置：0;  结束位置：-500逆向移动
				4. 鼠标进入轮播区域，暂停动画
```

