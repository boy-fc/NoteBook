# 1. HTML基础

## Web标准构成

​	结构HTML、表现CSS、行为JS     

## HTML语法骨架

```html
<HTML>   
    	<head>     
        		<title></title>
   		</head>
   		<body>
   		</body>
</HTML>
```

##  HTML标签的语义化

​	方便代码的阅读和维护

​	同时让浏览器或是网络爬虫可以很好地解析，从而更好分析其中的内容

​	使用语义化标签会具有更好地搜索引擎优化 

##  标签

​	双标签：<标签名> 内容 </标签名>

​	单标签：<标签名 />

###  标题标签

```html
			<hn> 标题文本 </hn>

				一般h1 都是给logo使用，或者页面中最重要标题信息。h1在一个页面只能使用一次,多次使用不利于seo(搜索引擎优化) 自然排名
```

### 	段落标签

```html
			<p> 文本内容 </p>
```

### 	 水平线标签

```html
			<hr />是单标签
```

### 	换行标签

```html
			<br />
```

### 	文本格式化标签

```html
			粗体<strong>文本内容</strong>  <b>文本内容</b>

  			斜体<em>文本内容</em>   <i>文本内容</i>

			删除线<del>文本内容</del>    <s>文本内容</s>

			下划线<ins>文本内容</ins>    <u>文本内容</u>

			上标<sup>文本内容</sup>		下标<sub>文本内容</sub>
```
### 	图像标签

```html
			<img src="图像URL" />
				src URL 图像的路径
				alt 文本 图像不能显示时的替换文本
				title 文本 鼠标悬停时显示的内容
				width 像素 设置图像的宽度
				heght 像素 设置图像的高度
				border 数字 设置图像边框的宽度
```

### 	 链接标签

```html
			<a href="跳转目标" target="目标窗口的弹出方式">文本或图像</a>
			target：用于指定链接页面的打开方式
			target_self:原窗口打开
			target_blank：新窗口中打开
```

### 	Base标签

```html
			<head> </head> 之间
```

### 	 锚点标签

~~~html
		1.使用相应的id名标注跳转目标的位置

  			<h3 id="two">第2集</h3> 

			```
		2.使用“a href=”#id名>“链接文本"</a>创建链接文本（被点击的）

			```
 			<a href="#two">
~~~

### 	 特殊字符标签

```html
		空格符  &nbsp;
		< 小于号  &lt;
		> 大于号  &gt;
		& 和号  &amp;
		¥ 人民币  &yen;
```

### 	 注释标签

```html
		<!-- 注释语句 -->  ctrl + /  或者 ctrl +shift + /
```

### 	div span标签

```html
		div
			分割， 分区的意思  其实有很多div 来组合网页
		span
		 	跨度，跨距；范围 （不跨行）
```

### 	列表标签

```html
				无序列表 ul 
				<ul>
  					<li>列表项1</li>
  					<li>列表项2</li>
  					<li>列表项3</li>
  					......
				</ul>
					<ul></ul>中只能嵌套<li></li>，直接在<ul></ul>标签中输入其他标签或者文字的做法是不被允许的
					<li>与</li>之间相当于一个容器，可以容纳所有元素
					无序列表会带有自己样式属性，放下那个样式，一会让CSS来

				有序列表 ol
				<ol>
 					<li>列表项1</li>
  					<li>列表项2</li>
  					<li>列表项3</li>
  					......
				</ol>

				自定义列表
				<dl>
 					<dt>名词1</dt>
  						<dd>名词1解释1</dd>
  						<dd>名词1解释2</dd>
  						...
 					 <dt>名词2</dt>
  						<dd>名词2解释1</dd>
  						<dd>名词2解释2</dd>
  						...
				</dl>
```

### 	表单域

```html
		收集的信息想提交,需要有form表单
		<form action="url地址" method="提交方式" name="表单名称">
  			各种表单控件
		</form>

		1.Action
			在表单收集到信息后，需要将信息传递给服务器进行处理，action属性用于指定接收并处理表单数据的服务器程序的url地址。
		2.method
			用于设置表单数据的提交方式，其取值为get或post(get 显示路径信息，post不显示路径信息)
		3.name
			用于指定表单的名称，以区分同一个页面中的多个表单
```

### 	下拉菜单

```html
		<select>
  			<option>选项1</option>
  			<option>选项2</option>
  			<option>选项3</option>
  			...
		</select>

		<select></select>;中至少应包含一对<option></option>
		在option 中定义selected =" selected "时，当前项即为默认选中项
```

### 	 textarea控件(文本域)

```html
		<textarea cols="每行中的字符数" rows="显示的行数">
  			文本内容
		</textarea>
```

### 	 label标签(理解)  

```html
		作用：  用于绑定一个表单元素, 当点击label标签的时候, 被绑定的表单元素就会获得输入焦点

		<!-- label for id   for="input 里边 id属性的值",作用是把label和input绑定,当点击label里边文字的时候,绑定的input会获取光标焦点 -->
```

### 	表单标签(掌握)	

```html
			表单控件
				包含了具体的表单功能项，如单行文本输入框、密码输入框、复选框、提交按钮、重置按钮等。

			提示信息
			 	一个表单中通常还需要包含一些说明性的文字，提示用户进行填写和操作。

			表单域
				相当于一个容器，用来容纳所有的表单控件和提示信息，可以通过他定义处理表单数据所用程序的url地址，以及数据提交到服务器的方法。如果不定义表单域，表单中的数据就无法传送到后台服务器。

			input 控件(重点)
				<input type="text">单行文本输入框
				<input type="password">密码输入框
				<input type="radio">单选按钮
					实现单选效果,必须将name值设置相同
					checked="checked" 设置默认选中项
				<input type="checkbox">多选框
				设置默认：checked="checked"
		
				<input type="button">普通按钮
				不能提交 配合js做特效
				<input type="submit">提交按钮
				<input type="reset">重置按钮
				<input type="image" src="图像路径">图像形式的提交按钮
				<in[put type="file">文件上传按钮
                    
			input 控件(重点)常用属性
				name 控件名称
				value 默认文本值
				size 控件显示宽度
				chenked 默认被选中项
				maxlength 控件允许输入的最大字符数
```



## 字符集

​	 gb2312 简单中文

​	 BIG5   繁体中文

​	GBK 中文字符兼容GB2312

​	 UTF-8 全世界所有国家需要用到的字符

## sublime快捷键

​	tab 补全代码

​	ctrl+shift+d 快速复制一行

​	ctrl+shift+k 快速删除一行

​	crlt+shift+↑(↓) 快速上移（下移）一行

​	ctrl+k+b 隐藏(显示)侧边栏

​	ctrl+L  快速选中一行

​	ctrl+h 查找替换

​	ctrl+f 查找

​	ctrl+鼠标单击  集体编辑

## 路径

### 	相对路径

```html
		1.	图像文件和HTML文件位于同一文件夹：只需输入图像文件的名称即可，如<img src="logo.gif" />
		2.	图像文件位于HTML文件的下一级文件夹：输入文件夹名和文件名，之间用“/”隔开，如<img 			src="img/img01/logo.gif" />
		3.	图像文件位于HTML文件的上一级文件夹：在文件名之前加入“../” ，如果是上两级，则需要使用 “../../”，以此类推，如<img src="../logo.gif" />
```

### 	绝对路径

​			绝对路径以Web站点根目录为参考基础的目录路径

## 	表格 table

```html
			创建表格
				<table>
  					<tr>
    					<td>单元格内的文字</td>
    					...
 					</tr>
  					...
				</table>

			table用于定义一个表格
 			tr 用于定义表格中的一行，必须嵌套在 table标签中，在 table中包含几对 tr，就有几行表格
			td /td：用于定义表格中的单元格，必须嵌套在<tr></tr>标签中，一对 <tr> </tr>中包含几对						<td></td>，就表示该行中有多少列（或多少个单元格）
			 <tr></tr>中只能嵌套<td></td><th></th>
			<td></td>标签，他就像一个容器，可以容纳所有的元素

			表格属性
				border 设置表格的边框（默认border=“0”无边框）
				cellspacing 设置单元格与单元格边框之间的空白间距
				cellpadding 设置单元格内容与单元格边框之间的空白间距
				width 设置表格的宽度
				height 设置表格的宽度
				align 设置表格在网页中对齐方式的（left、center、right）

			表格标题
				<table>
   					<caption>我是表格标题</caption>
				</table>

				caption 标签必须紧随 table 标签之后。您只能对每个表格定义一个标题。通常这个标题会被居中于表格之上

			表头标签
				表头一般位于表格的第一行或第一列，其文本加粗居中，表头标签<th><th>替代相应的单元格标签<td><td>即可
                    
			表格结构（了解）
				<thead></thead>：用于定义表格的头部

				必须位于<table></table> 标签中，一般包含网页的logo和导航等头部信息
				<tbody></tbody>：用于定义表格的主体

				位于<table></table>标签中，一般包含网页中除头部和底部之外的其他内容
                    
			合并单元格(难点)
		 		跨列合并：colspan 
				跨行合并：rowspan 
```

