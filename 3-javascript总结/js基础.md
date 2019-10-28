# JS基础

## 基本操作

### 	介绍

​					一门运行在浏览器端的脚本 编程 语言

### 	引入方式

#### 		内嵌式 		

```js
			  //demo学习阶段的主要写法
			  <script>
				 alert('hello world');
			  </script>
```
####  		外链式

```js
			//新建一个JS文件，文件里JS的代码，引入HTML页面内；作为个文件可以重复使用，项目开发阶段使用
			<script sr<script src="./01-demo.js"></script>c="./01-demo.js"></script>
```

#### 		行内式 

```js
			//了解，一般不用
			<input type="button" value="点我" onclick="alert('helloworld')">
```

### 	JS 注释

```js
			//1.单行注释：一般是用于简单的注释
				ctrl + /
			//2.多行注释：大段落的注释，用于文档说明，后面函数方法的说明
				ctrl + shift + /
```

### 	输入输出

```js
			prompt("输入框的提示内容");
			alert('要输出的内容')  
			//浏览器会有个弹窗，只要不点击弹窗，后面就不会执行；alert 警告
			console.log('要输出的内容')；  
			console.log('要输出的内容',1);   可逗号隔开，输出多个值；
			//在控制台输出，不阻止下面的执行。调试常用 console控制台 log 日志；！！！
			document.write('<div>文字</div>')
			//在页面body中显示，把解析HTML结构；
```

## 变量

### 		语法

```js
		1.var 声明变量
		  var 关键字 声明变量
		2.配合输入
		  var pwd = prompt('请输入您的卡密码')
		  alert(pwd);
		3.过程
		  var a = 1;
  		  var a; 声明变量；
  		  a = 1; 给变量赋值
		4.赋值后，可以再次赋值
		  var b = "我";
 		  console.log(b);
  		  再次重新赋值，以后b一直是200；
  		  b = 200;
 		  console.log(b);
		5.声明时赋值
		  var a = 1;
```

### 		命名

​		1. 变量名字不能用数字作为开头

​		2. 不能用关键字 保留字

```js
		  var var = 10;
```

​		3. 区分大小写,根据英文场景，一般用英文

​		4.**驼峰**：主要是为了你开发方便，推荐

### 		交换值

​		1.新声明个变量C；
​		2.把A变量赋值过去给C；
​		3.把B变量给A，把C变量值给A；

### 		补充

​		1 变量可以一次性声明多个
​		 2 还可以声明多个的同时进行赋值
​		3 变量也可以作为另一个变量的值

## 数据类型

### 		基本类型

#### 				数字(number)类型

​				所有的数字都是数字类型

​				NaN：not a number，不是某个数，泛指，不知道指哪个数，但是为数字类型

#### 				字符串(string)类型

​				语法：一定要带引号，单双无所谓；只要你戴上引号，就是字符串

​				程序中，默认把一对引号，认为就是字符串的结束

​				单双引号可以相互包着，能显示

​				转译字符：把特殊的字符转成 JS 可以读的字符

​				特殊的字符：`""  '' \

```js
				console.log("小明说:\"小红明天真漂亮\"");
```

#### 				布尔(boolean)类型

​				标示某个结果，存在或者不存在（不成立、假）；只有两个值  true  false

#### 				null值

​				值：null用来表示尚未存在的对象（复杂类型）专门赋值为null

#### 				undefined类型

​				undefined类型：undefined值

​				变量没有赋值，也不知道是啥，不是空；默认赋值为undefined	

```js
				var a;
				console.log(a);// 输出undefined
```

### 		3.2 查看数据类型

```js
				typeof 数据;
				typeof(数据);
```

### 		数据类型转换

#### 				其他类型转数字类型

```js
 				Number()
				结果：数字/NaN
```

```js
				parseInt()
				将其他类型为数字整数
				只能接受字符串，纯字符串、true、null、undefined都是NaN
				如果字符串前面是数字，可以把前面的数字转化为数字类型
				如果字符串中前面不是数字，转NaN
```

​			

```js
				parseFloat()
				parseFloat这个方法用于转换字符串转换成小数(在编程中，小数也称浮点数)
				非数字类型只能接受**字符串**，纯字符串、true、null、undefined都是NaN
				如果字符串前面是数字，可以把前面的数字转化为数字类型
				如果字符串中前面不是数字，转NaN
```

#### 		其它类型转字符串类型

```js
				String()
				特点：有引号就行了
				语法：转呗；反正最后就是用单双引号包起来了		
```

```
				.toString()
				语法：undefined和null不能使用这个方式变成字符串；因为后面undefined和null没有该方法
```

#### 		其它类型转布尔类型

​				Boolean()

​				转 Boolean 结果：存在 不存在 返回就是一个布尔值

​				逻辑：只要是确认的，存在的数据，都是ture

```js
 			  6中情况转false 
				// var res = "";完全空字符
  				// console.log(res, Boolean(res));

  				// var res = 0;
  				// console.log(res, Boolean(res));

  				// var res = NaN;
  				// console.log(res, Boolean(res));

  				// var res = null;
  				// console.log(res, Boolean(res));

  				// var res = undefined;
  				// console.log(res, Boolean(res));

  				// var res = false;
  				// console.log(res, Boolean(res));
```

## 操作符

### 		算术操作符

```js
			常规
				// var a = 1 - 1;
  				// var b = 10 / 2;
  				// var c = 5 * 4;
  				// var d = 7 % 3;
```

```js
			非常规
				字符串遇见+：左右临近的类型都会转换为字符串,从左到右执行，数字相加，字符串拼接
				字符串遇见- / * %：参与运算，我们要的数据类型，字符串隐式转换为数字类型
			**隐式转换**
				 数字  "1000"隐式转换为1000
				 "abc"隐式转换为NaN
				 null 隐式转数字 0
				 Boolean 隐式转数字 0 或者1
				 undefined 隐式转数字 NaN

```

​			**自增++、自减--**

```js
				a++: 参与运算的时候，会先用原来的值先运算，再自增；（写在后面就后加）
				var a = 10;
				var b = a++ + 10; 
				// 运算的时候，使用a的原来值10参与加法运算，10+10赋值给b之后，再实现a的自增
				console.log(b); // 输出20
				console.log(a); // 输出 11

				++a: 参与运算的时候，会先在原来的基础上自增，再使用新的值参与运算（写在前面就先加）
				var c = 10;
				var d = ++a + 10; 
				// 运算的时候，先执行a的自增，再使用a自增后的值11和10相加，最终结果是 11 + 10
				console.log(d); // 输出21
				console.log(c); // 输出11
```

### 	比较操作符

#### 			**>  <  >=  <=**	

```js
			常规操作：比数字类型
				返回:这个比较后的结果状态 Boolean；
			
			非常规
				比较运算符：两边都是需要数字类型；
				不是数字类型， 隐式转化 为 数字类型
```

#### 			**==**	

```js
 			// 先看类型:
  			// 1.若类型相同，比值；
  			// 2.若类型不同，隐式转化 数字类型
			// undefined和null与其他数在进行相等判断时不进行类型转换。
			console.log(null==0)         //false
			console.log(0 == undefined); //false
			// ECMAScript认为undefined是从null派生出来的，所以把它们定义为相等的;
			console.log(null==undefined)  // true
```

#### 			===	

```js
			// 先看类型:
  			// 1.如果类型相同，比值；
  			// 2.如果类型不同，直接false;
```

### 	逻辑运算符

#### 	 		&& 且 

​				 **全部满足** 

​		 		常规：需要Boolean值进行逻辑判断

​				 返回：把最后一个满足的结果，返回过来

​				 返回：当遇见不满足情况，直接就把不满足结果返回；

​				 遇见：非Boolean值；转换为布尔值参与逻辑判断

#### 	 		|| 或

​				**满足一个条件即可**

​				特点：只有有一个true，那么就直接返回是true的这个结果

#### 			! 去反

​				常规Boolean值去反

### 	赋值运算符

​				**+=  -=  *=  /=  %=**

### 	优先级

#### 				大致优先级

​					括号先算

​					其次算算术：++a优先;

​					再次算比较  > ==

​					然后算逻辑 && ||

​					最后算赋值 =

#### 				 具体计算优先级

​					1. 第一优先级： [] . ()

​					2. 第二优先级： ++ -- !

​					3. 第三优先级： *  /  %

​					4.  第四优先级： +  -

​					5. 第五优先级： >   >=   <   <=

​					6. 第六优先级： ==   !=    ===    !==  

​					7. 第七优先级： &&

​					8.第八优先级： || 

​					9.第九优先级： = += -= *= /= %=  

## 结构

​		分支结构：不同的情况下，走不同的分支

​		循环结构：重复做一件事情，其作用就是用来重复执行代码的

​		顺序结构：程序默认就是由上到下顺序执行的

### 		分支结构

#### 				if结构	

```js
			if(条件表达式){
   				// 当 条件表达式 的结果是 true 时 执行的代码
			}
```

```js
			if(条件表达式){
   				//当条件表达式的结果是 true 时执行的代码
			}else {
 			 	//当条件表达式的结果是 false 时执行的代码
			}	
```

```js
			if(条件表达式1){
   				//当条件表达式1的结果是 true 时执行的代码
			}
			else if(条件表达式2){
  				//当条件表达式2的结果是 true 时执行的代码
			}
			else if(条件表达式3){
  				//当条件表达式3的结果是 true 时执行的代码
			}
				// 中间可以继续写多个判断 ...
			else {
  				// 多个条件表达式的结果都是 false 的时候执行的代码
			}
```

#### 			switch-case结构

```js
			switch （数据）{
  			case 固定值1: 
    		// 当数据 === 固定值1时执行的代码; 先看类型，看值；
    		// 表示当前 情况结束；
    		   break;
  			case 固定值2: 
    		// 当数据 === 固定值2时执行的代码;
    		   break;
  			case 固定值3: 
    		// 当数据 === 固定值3时执行的代码;
   		 	   break;
  			// 中间还可以写多个判断
  			default : 
    		// 当数据和上面的所有固定值都相等的时候执行的代码
    		   break;
			}
```

### 	循环结构

#### 			while循环

```js
			// 条件表达式结果需要布尔值，若不是Boolean值，隐式转化；
			while (条件表达式){
  				// 循环体就是重复执行的代码
```

​				特点：
​					设置为true，容易卡死
​					设置false，直接就不执行

#### 			for循环

```js
			for(初始化表达式; 条件表达式; 自增表达式){
  				循环体
			}
```

#### 			do-while循环

```js
			do {
  				循环体
			}while(条件表达式)
```

#### 			break

```js
			break用于结束整个循环
			break后面的代码都不会执行，执行前面的代码
```

#### 			continue

```js
			continue用于结束整个循环中的一次，结束当前这次循环；
			continue后面的代码都不会执行，执行前面的代码
```

## 表达式

​		在js代码中，只要可以返回一个**结果**的，都可以称为一个表达式

​		技巧：在浏览器后台可以直接敲表达式，回车返回的就是该表达式的结果

### 		三元表达式

​			表达式：有值会返回

​			语法：if else 的简写；有返回值

```js
		  // 首先 要知道 表达式 会返回结果；
		  // 这个表达式会先执行表达式1，判断其结果是true还是false，
		  // 如果是true，则执行表达式2，然后将 表达式2的执行结果 作为整个三元表达式的结果，
		  // 如果是false，则执行表达式3，并 表达式3的结果 作为整个三元表达式的结果
		  //例如： 求二个数字中谁更大
					var a = 10; var b = 20;
					var max = a > b ? a : b;
					console.log(max);
```

## 数组

### 		介绍

​			数组是一个有顺序、有长度的数据集合

### 		声明

​			声明一个数组，字面量的形式 ：var arr = [ ];

​			输出 [ ]  这是一个没有数据在里面的数组，称为空数组

### 		存值

​			数组中的数据使用索引管理

​			索引就是序号、顺序、排位、位置

​			索引从0开始

​			把   **数组[索引**]  格式当成一个变量使用就行

​			如果一开始就知道数组了，可以直接使用一个简单的语法存储数据 var arr = [91,88,72,45,63];

​			上面每个位置上存的都是数字类型，可以为其他类型

### 		取值

​			数据取值同样使用索引取

### 		遍历

​			使用循环来遍历数组，当数组中的数据比较多的时候，会比较方便。一般是使用for循环

### 		数组长度

​			数组中一共存放了多少数据

​			最大索引总是比长度少 1 		

```js
			案例：求数组中所有数字的总和的平均值
				var sum = 0;
				for(var i =0; i < arr.length; i++){
  					sum += arr[i];
				}
				console.log(sum);
				// 求平均分
				// 平均分= 总分 / 数组的长度
				var avg = sum / arr.length;	
```

```js
			案例：求数组中的最大值
			分析：生活中，一堆人最高的（人很多，多到你一下看不出来）；

			- 最大值：最起码得两个数比较下，得到最大值；
			- 假设：其中随便一个是最大值MAX，每个元素和max比较，
			- 若有比MAX大的，那该元素代替MAX；
			- 若都没有MAX大，恭喜，你一开始就猜对了；
  				var max = arr[0];
 				for(var i =0; i < arr.length; i++){
  				if(max < arr[i]){
    				max = arr[i];
  					}
 				}
```

```js
			案例：求数组中的最大值的索引
			分析：找打最大值的时候，记录下最大值的下标就行了。
				var max_index = 0;
				var max = arr[max_index];
				for(var i =0; i < arr.length; i++){
					if(max < arr[i]){
  						max = arr[i];
  						max_index = i;
					}
				}
```

### 		数组的构造函数

```js
			// 使用 构造函数 创建数组
  			var arr = new Array();
  			
			arr[0] = 10;
			arr[1] = 20;
			console.log(arr);
			var arr = new Array(10,20);
			console.log(arr);
```

​			注意：一个数据，不要使用这个方式存储数据；它会认为你想要设置数组的长度，而不是要把数据存储在数组中		

```js
			var arr = new Array(10);
			console.log(arr); // 输出 [empty × 10]
```

## 函数

### 		介绍

​			把一段相对独立的具有特定功能的代码块封装起来，形成一个独立实体，起个名字（函数名），在

​		后续开发中可以随时反复调用

### 		作用

​			封装（包起来）一段代码，将来可以随时拿来使用

### 		封装

​			功能要单一

### 		语法

​			function 关键字 用于声明函数

​			调用：声明的函数，一段代码被包起来；需要被调用，才能执行当前的函数

### 		函数参数

​			函数内部的变量

```js
			// 在小括号内的变量，对于函数来说，就是参数；
			// 参数就是函数 内部的变量；
			function 函数名(参数){
  				函数体
			}
```

​			配置：把你要抽象的数据配置为参数，记得要放入声明函数时，后面的（）	

​				    根据你的业务需求，把一些你要抽象的数据，配置为参数。

​		  		  记得：在函数的()内，写上你配置的变量名；

​	    			在声明函数的，内部的变量才算是声明了。	

```js
			// 函数声明，配置两个参数：
  			function tell_story(name_1, name_2) {
    		// 函数体；
    		console.log("山上有庙");
    		console.log("庙有和尚");
    		console.log(name_1 + "说事");
    		console.log(name_1 + "对" + name_2 + "说：");
  			}
			// 调用函数
  			tell_story("铁头", "熊大");	 
```

​			不赋值
​				变量：函数内部的变量，没有赋值，默认为undefined

​				解决：对参数进行判断，如果是undefined，给一个默认值

​			**形参与实参**

​				要传入的数据是简单数据类型数据，形参与实参相互不影响

​				形参：形式上参数，函数内部声明的变量，只能在内部使用，用于参与逻辑过程

​				实参：调用函数时，真实参与运算的数据，可以为传入数据，也可以传变量

### 		返回值

​			函数执行完毕，会得到一个结果，这个结果就是函数的返回值

​			return:作用1：返回值，必须后面跟一个值；即将要作为函数执行完后，返回的值

​			return作用2：终止函数的执行,函数内部下面的代码不执行了

### 		函数表达式

```js
			var 函数名 = function (参数){
 				//函数体
			}
            
			//匿名函数
			//JS内不允许匿名函数单独存在
			function() {} 
```

### 		函数类型

​			在js中，只要是一种数据类型的，都可以作为函数的参数	

```js
			function fn(){}
			console.log(typeof fn); // 输出 字符串的  function
```

#### 			回调函数	

```js
			// fn 只不过在函数内部是一个形参，内部变量；
			function f1(a,fn){
  			console.log(a);
  			// 函数的调用，在函数名的后面加括号；
  			// 内部的函数对外面的函数叫回调函数；
  			fn(); 
			}

			function f2(){
  				console.log('f2函数执行了');
			}
			f1(10,f2);// 输出 10 和 'f2函数执行了'
```

### 		作用域

​			作用范围，能生效的范围

#### 				全局作用域

​			全局作用域：能在页面的任何位置都可以访问	

```js
			var a = 10;
			function f1(){
  				console.log(a);
			}
			f1();// 变量a在函数外定义，可以在函数内使用
```

​			全局变量：在全局作用哉下声明的变量；

#### 				局部作用域

​			局部作用域：只能在局部的作用域范围进行访问

​			局部变量：在局部作用域下声明的变量

```js
			function f2(){
  				var b = 20;
			}
			// 变量b在函数内定义，在函数外无法访问，报错： b is not defined
			console.log(b); 
```

### 		预解析

​			提前、解析（分析）会把初始化的声明的变量、函数，全部提升到当前作用域的最顶端

```js
		  // 观察下面的代码，说出执行结果
		  var num = 10;
		  fun();

		  function fun() {
  			console.log(num);
  			var num = 20;
		  }

		  // ------------------------------------------------------------变量提升的演示
		  // 预解析：先把你声明变量、函数先全部提升到你当前的作用域的最顶端；
          var num;

		  function fun() {
    		var num;
    		console.log(num);
    		num = 20;
		   }
		  // 赋值；
		  num = 10;
		  // 函数调用；
		  fun(); // 输出 undefined；
```

##   arguments

​		获取所有`实参`的对象，函数内部的变量（不是我们声明的，也不需要我们声明）

```js
		function fn(){
		console.log(arguments);
		}
		fn(1); // 输出 [1]
		fn(1,2) // 输出 [1,2]
		fn(1,2,3,4,5) // 输出 [1,2,3,4,5]
```

​		arguments 这个东西看起来**样子像数组**，但是其实不是一个数组，我们管它叫 `伪数组`。它具有数组的长度和顺序等特征。本质为对象	

```js
		//arguments 伪数组可以**循环遍历
		function getSum(){
  			var sum = 0;
  			for(var i = 0; i < arguments.length ; i++){
    			sum += arguments[i];
  			}
  			return sum;
		}
```

## 对象

### 		对象简介

​			核心概念：**万物皆对象**，我们在编程中，使用对象来描述万事万物

​			对象：使用属性描述事物的特征，使用方法来描述行为， 就是对象这种语法

​			对象：属性和方法的集合

​			特点：实现高效开发，便于维护

### 		对象语法

#### 			创建

```js
		//构造函数
			var obj = new Object(); // 这是一个没有属性和方法的对象
		//字面量
			var obj = {}; // 这也是一个没有属性和方法对象，其本质和构造函数创建的对象是一样的
```

#### 			添加

​		使用对象描述一个叫`狗蛋`的人，先字面量声明一个对象，再给对象上属性和方法赋值		

```js
	   	var obj = {};

		// 对象.属性 = 值;
		obj.name = '狗蛋';// 名字是一个人的特征

		// 对象.方法名 = function(){}
		// 注意：该方法后面的的赋值为一个函数，函数在什么时候执行？调用的时候才会执行；
		obj.sayName = function(){  // 人会说出自己的名字，也就是人有自己的行为
			console.log('你好，我叫' + obj.name);
		}
```

​		通过字面量初始化对象时，初始化属性

```js
		// 描述一个学生
		var student = {
  		name : '狗蛋',
  		age : 12,
  		gender : '男',
  		sayName : function(){
   			console.log(student.name);
  		  }
		}
```

​		一个属性和一个值叫键值对。多个键值之间使用逗号分隔，键的方式添加属性		

```js
		// 对象[属性名]  属性名必须是String类型，里面可以写字符串；
		var obj = {};
		obj['name'] = '狗蛋';
		obj['sayName'] = function(){
  			console.log('你好，我叫' + obj['name']);
		}
```

#### 			获取

##### 					点属性访问

```js
			// 得到对象的名字,属性可以当成变量使用
			console.log(obj.name);
			// 调用对象的方法，方法的本质是函数
			obj.sayName();
```

##### 					以键的方式访问属性

```js
			console.log(obj['name']);
			obj['sayName']();
```

#### 			遍历

​			数组可以遍历；对象也可以遍历	

```js
			// key 就是obj这个对象中的每个键，obj就是要遍历的对象。
			for(var key in obj){
			}

			var obj = {
  				name : '狗蛋',
  				age : 12,
  				gender : '男'
			};
			for(var key in obj){
  				console.log(key);
  				// 只能通过键的方式获取值
  				console.log(obj[key]);
			}
```

### 		对象类型

#### 				简单类型

​				数据存储在内存的栈空间中

​				简单类型的的变量赋值给另一个变量，当另一个变量改变了，不会影响原来的变量

```js
				var a = 10;
				var b = a;
				b = 20;
				console.log(a,b); //输出 10，20 也就是说，a的值不会受到b的值的改变而影响
```

#### 					复杂类型

​				数据存储在内存的堆空间中

​				复杂类型在内存的储存，赋值给其他变量，也是把格子内的内容复制了一份

​				相当于两个对象内容存的是同一份地址

```js
				var obj1 = {
  					name : '狗蛋'
				};
				var obj2 = obj1;
				obj2.name = '翠花';

				// 输出 两个翠花 ， 也就是说，obj1的name属性受到了obj2的name属性影响
				console.log(obj1.name,obj2.name); 
```

## 方法

### 		内置对象

​			对象：属性和方法的集合体；我们关注如何使用就可以

​			内置：JS语法给我封装好了一些对象，里面提供了很多常用、实用的属性和方法

### 		Math

#### 				Math.random(x)

​				生成一个 [0,1) 之间的随机浮点数	

```js
				var r = Math.random();
				// 每次执行等到的数字都不一样
				console.log(r);
```

```js
			随机色案例：
			function getColor() {
    			var res = Math.random() * 256;
    			res = Math.floor(res);
				return res;
             }
  			var color =`rgba(${getColor()},${getColor()}
                       ,${getColor()},${Math.random()})`;

 			// console.log(color);

  			// 字符串拼接：'rgb(120,120,110)'; 
  			// document.write()
  			document.write(`<div style="background:${color}"></div>`);
```
####  				Math.floor(x) 

​				一个浮点数进行向下取整

```js
			console.log(Math.floor(3.1));  // 3
			console.log(Math.floor(3.9));  // 3
			console.log(Math.floor(-3.1)); // -4
			console.log(Math.floor(-3.9)); // -4
```

#### 				Math.round(x)

​				一个浮点数进行四舍五入取整

```js
			console.log(Math.floor(3.1));  // 3
			console.log(Math.floor(3.9));  // 4
			console.log(Math.floor(-3.1)); // -3
			console.log(Math.floor(-3.9)); // -4
```

#### 				Math.ceil(x)

​				一个浮点数进行向上取整

```js
			console.log(Math.ceil(3.1));  // 4
			console.log(Math.ceil(3.9));  // 4
			console.log(Math.ceil(-3.1)); // -3
			console.log(Math.ceil(-3.9)); // -3
```

#### 				Math.abs(x)

​				求一个数的绝对值 正数	

```js
			console.log(Math.abs(3));  // 3
			console.log(Math.abs(-3)); // 3
```

#### 				Math.max(x,y...) 

​				求多个数字中的最大值，同理 Math.min(x,y...)

```js
			console.log(Math.max(10,20));  // 20
			console.log(Math.max(8,4,5,7,3)); // 8

			console.log(Math.min(10,20));  // 10
			console.log(Math.min(8,4,5,7,3)); // 3
```

### 		11.3 Date 

```js
			var date = new Date(); // 得到的是当前时间的日期对象
```

​			获取年月日时分秒	

```js
			console.log(date.getFullYear());// 年份
			console.log(date.getMonth()); // 月份，从0开始

			// 当前日 为什么不是getDay() 英语：日期date，day某天；
			console.log(date.getDate()); 

			console.log(date.getHours()); // 小时，0-23
			console.log(date.getMinutes()); // 分钟 ， 0-59
			console.log(date.getSeconds()); // 秒数 ， 0-59
			console.log(date.getMilliseconds()); // 毫秒 0-999 ， 1秒 = 1000毫秒
```

​			创建一个指定日期的对象	

```js
			// 给一个日期格式字符串
			var date = new Date('2019-01-01');

			// 分别传入年月日时分秒。注意传入的月份是从0开始算的
			var date = new Date(2019,0,1,12,33,12);
```

​			获取从1970年1月1日到现在的总毫秒数，常说的时间戳

```js
			var date = new Date();

			console.log(date.valueOf());
			console.log(date.getTime());
			console.log(1*date);

			console.log(Date.now());
```

### 		String

#### 					字符串不可变

​					旧的字符串赋值在一个变量上，给变量重新赋值新的字符串（完全新的字符串，或者拼接

​					后字符串），旧的字符串不是被覆盖；在内存的游离状态

​					所以尽量避免大量使用字符串的拼接；这个算性能优化的一点

#### 					查找字符

##### 										charAt	

```js
					// 这个方法用于获取字符串中位于指定位置的字符
					var str = '我爱中华人民共和国';
					console.log(str.charAt(2));
```

##### 										charCodeAt

```js
					// 这个方法用于获取字符串中位于指定位置的字符的ASCII码
					var str = 'abcdef'
					console.log(str.charCodeAt(0));
```

#### 					split	

​			split(“ ”) 方法用于把一个字符串分割成字符串数组

```js
 					// 地址上有参数的 字符串
  					var str = 'b.com?name="张三"&age=16';
  					// 1.先用 ? 进行字符串分隔，把后面的参数分隔；
  					var arr_1 = str.split("?");
  					// 2.这个地方分隔出来是长度为2的数组，取到最后一个数据
  					// name="张三"&age=16
  					var str_1 = arr_1[1];
  					// 3.对 取到的数据，也就是这个字符串进行 新 的分隔；得到新的数组；
 					// 数组为 ['name="张三"','age=16']
  					var arr_2 = str_1.split("&");
  					// 4.数组的循环;
  					var obj = {};
  					arr_2.forEach(function(item, index) {
    				// 5.在循环体内部，进行每个数据的再次分隔；
    				// 比如：'name="张三"'  进行 = 分隔；
    				// 分隔后得到数组  为 ["name","张三"]
    				var res = item.split("=");
    				// 数组 第一个位置 键key, 第二个位置 值value；
    				var key = res[0];
    				var value = res[1];
    				// 给对象的属性进行赋值；
    				obj[key] = value;
  					});
```

#### 					拼接与截取

##### 									+

##### 									concat 拼接		

​			concat() 方法用于连接两个或多个数组。

​			该方法不会改变现有的数组，而仅仅会返回被连接数组的一个副本。

```js
					// 这个方法用于连接多个字符串，其作用相当于 + 操作符
					var res = "abc".concat('def','ghi');
					console.log(res);
```

##### 									substring 截取字符串

```js
					// 不操作原字符串；返回截取出来的字符串
					// 这个方法用于获取字符串中的部分字符
					var str = '我爱中华人民共和国';

					// 从索引2开始，到索引4结束，得到之间的字符，不包含索引4的字符
					var res = str.substring(2,4);
					console.log(res);
```

##### 									slice 	

```js
					// 这个方法用于获取字符串中的部分字符
					var str = '我爱中华人民共和国';
					var res = str.slice(2,4);
					// 从索引2开始，到索引4结束，得到之间的字符，不包含索引4的字符
					console.log(res);

					// 看起来和substring 没有啥区别，
					// slice()可以设置参数为负数，slice()方法在遇到负的参数的时候，会将这个负值与字						符串的长度相加。
					console.log(str.slice(-6,7));
					console.log(str.slice(2,-5));
					console.log(str.slice(-9,-7));
```

##### 									substr 	

substr() 方法可在字符串中抽取从 *start* 下标开始的指定数目的字符。

```
stringObject.substr(start,length)
```

```js
					// 这个方法用于获取字符串中的部分字符
					var str = '我爱中华人民共和国';
					var res = str.substr(2,2);// 索引2开始，总共获取2个字符，第二个参数为个数
```

### 		Array

#### 			push

​				从数组后面推入一个元素或多个元素

​				返回：修改后数组的长度

#### 			pop

​				删除数组最后一个元素

​				返回 被删除的元素

#### 			unshift

​				从数组前面添加一个或多个元素

​				返回：修改后数组的长度

#### 			shift

​				用于将数组的第一个元素移除

​				返回 被删除的元素

#### 			splice

​				从数组的指定位置移除、添加、替换元素

​		 		返回 被移除数据的数组

```js
 				// splice:删除
  				删除一个元素
  				// var res = arr.splice(3, 1);
  				// console.log(arr, res);

 				作用：第一个参数是下标；被删除数据的个数；
  				// 返回值：被删除数据的数组；
  				// var res = arr.splice(3, 2);
  				// console.log(arr, res);

  				// 添加数据
  				// 下标3：代表第四个位置，
  				// 第二个参数：删除0个；
  				// 从下标3的位置，添加后面的数据（第三个和第三个参数）
  				// var res = arr.splice(3, 0, "abc", "def");
  				// 返回的是空数组；
  				// console.log(arr, res);

  				// 修改，替换数据
  				// 逻辑：删除的逻辑。
  				// 把删除的位置的数据，替换为其他数据；
  				// var res = arr.splice(3, 1, "abc");
  				// console.log(arr, res);
```

#### 		查找元素

​		**indexOf**：根据元素查找索引，如果这个元素在数组中，返回索引，否则返回-1，找元素在不在数组内部

```js
				var arr = [10,20,30]
				console.log(arr.indexOf(30));  // 2
				console.log(arr.indexOf(40));  // -1
```

​		**findIndex**：用于查找满足条件的第一个元素的索引，如果没有，则返回-1	

```js
				var arr = [10, 20, 30];
				var res1 = arr.findIndex(function (item) {
  					return item >= 20;
				});
				// 返回 满足条件的第一个元素的的索引
				console.log(res1);  

				var res2 = arr.findIndex(function (item) {
  					return item >= 50;
				});
				// -1
				console.log(res2);
```

#### 		遍历数组

##### 				for循环：JS基础语法

##### 				forEach：遍历数组

```js
				// 数组的 forEach 方法用于遍历数组
				var arr_1 = [10,20,30,40,50];

				// forEach方法需要一个参数是一个函数，这个函数也接收3个参数，
				// item是数组中的每个元素，index是item的索引,arr表示当前数组；
				// 对本数组操作，没有返回值；
				arr_1.forEach(function(item,index,arr){
  					console.log(item,index);
				});
```

##### 				filter ：筛选数组

​				筛选出数组中满足条件的数组，返回是一个新的数组

```js
				// 数组的filter方法用于将数组中满足条件的元素筛选出来
				// 筛选出数组中 小于 2000 的数据
				var arr_1 = [1500,1800,2200,300,2600,800];
				var res = arr_1.filter(function(item,index,arr){
  					return item < 2000;
				});
				// fitler方法的的参数要求是一个函数，这个函数接收2个参数：item是数组中的每个元素，					index是item对应的索引,arr代表当前的数组

				// 复制一个数组
				var arr_1 = arr_2.filter(function(item,index,arr){
  					return item;
				});
```

##### 				拼接与截取

​		concat  拼接数组，不改变原数组，创建新数组返回	

```js
				// 数组的concat方法的作用是把多个数组合并成一个新的数组
				var arr1 = [1,2,3];
				var arr2 = [4,5,6];
				var arr3 = [7,8,9];
				var res = arr1.concat(arr2,arr3);
				console.log(res);

				// 复制一个数组
				var arr_1 = arr.concat();
```

​		slice 截取数组：不对原数组操作，返回的是新的数组；

```js
				var arr = ['a','b','c','d','e'];
				// 表示 从下标1（包括），截取到下标为4(不包括),
				var res = arr.slice(1, 4);

				// 如果不给第二个参数，默认就是把从start开始，到length结束的所有的元素截取
				var arr_1 = arr_2.slice(1);

				// 复制数组：如果省略两个参数，start默认是0，end默认是length
				var arr_1 = arr_2.slice();
```

##### 				复制

###### 						for循环

```js
 				// 如何复制一个数组；
  				var new_arr_1 = [];
  				for (let index = 0; index < arr.length; index++) {
    				new_arr_1[index] = arr[index];
  				}
```

###### 						forEach : 变量

```js
				// forEach : 变量
  				var new_arr_2 = [];
  				arr.forEach(function(item, index) {
    				new_arr_2.push(item);
  				});
```

###### 		 				filter:数组过滤

```js
  				// filter:数组过滤：满足条件返出来，返每个元素，返到新数组；
  				var new_arr_3 = arr.filter(function(item, index) {
        			return true;
  				});
```

###### 			 			concat

```js
 				// concat: 不对原数组操作，返回是一个新的数组；
  				var new_arr_4 = arr.concat();
  				// console.log(new_arr_4);
```

###### 						slice

```js
 				// slice :截取 不对原数组操作，返回是一个新的数组；
  				var new_arr_5 = arr.slice();
```

### Object复制	

```js
 			// JS 浅拷贝；
  			var new_obj = {};
  			for (var key in obj) {
    			// console.log(key, obj[key]);
    			new_obj[key] = obj[key];
  			}
```

### 	数组、字符串互转

#### 			join 

​			用于将数组中的多元素以指定分隔符连接成一个字符串

```js
			var arr = ['刘备','关羽','张飞'];
			var str = arr.join('|'); 
			console.log(str);  // 刘备|关羽|张飞
```

#### 			split 

​			字符串的方法：转数字，后面为分隔的字符	

```js
			// 这个方法用于将一个字符串以指定的符号分割成数组
			var str = '刘备|关羽|张飞';
			var arr = str.split('|');
			console.log(arr);
```

## 案例-小娜V1.0	

### 	需求

​			输入q：完全退出；

​			输入1：得到求和功能，我们输入"数字,数字,数字"的格式，帮我们计算出我们的输入的和；

​			输入2：获得当前时间；

​			输入3：随机给我讲一个笑话；

​			不q：一直循环提示 可以 输入1/2/3、q这些功能点；

### 	功能

#### 		循环与退出

```js
				//1.使用wihle，设置条件为true，一直循环

				while(true){
				}
```

```js
				//2.在内部使用变量接受用户输入的信息，使用if else（）判断用户输入的是哪种情况

				 while (true) {
        			// 输出提示框信息提示
        			var info = prompt("你好，我是小娜v1.0\n输入q:退出程序\n输入1：求和\n输入2：获									取时间\n输入3：讲个笑话");
        			// 退出功能实现
       				if (info == "q") {
            		alert("你不爱小娜了吗？再见！！！");
            		break;
        			}
                } 
```

```js
				//3.退出功能：使用break退出while
```

#### 		2.2 求和

```js
				//输入1，进入求和功能
				//注意： 输入的都是字符串，所以这里要使用字符串比较
				case '1':
				var nums = prompt('请输入要求和的数字，以逗号隔开，例如： 1,2,3,4');
				break;

				我们输入"数字,数字,数字"的格式，需要转为数组，求和
				var str = '12,88,72,6';
				// 以逗号为分隔符，分割字符串，得到一个数组
				// 字符串.split(指定分隔符)
				// 后面的指定分隔符就是我们写字符串数字与字符串数字之间的间隔符号
				var arr = str.split(',');

				// 输出 ['12','88','72','6']
				// 转为数组，但不是说里面的元素转为数字类型了；

				//求和：循环、每个元素转类型
				sum += parseFloat(arr[i]);
```

#### 		2.3 获取时间	

```js
			//输入2，获取当前时间
			//在js中，要获取系统的当前日期和时间，需要用到一个js自带的**Date对象

			//为了格式上的好看：单位数，补位成双位数
			if(day < 10){
    			day = '0' + day;
			}

			// 创建Date对象
			var date = new Date();
			console.log(data); // 系统时间不同，输出的结果也会不同，但是都是输出当前系统的时间

			// 获取时间对象的各个部分，对象.方法();

			// 获取年份
			var year = date.getFullYear();
			console.log(year);

			// 获取月份 ， 得到的月份是从0开始的 ，使用 0-11 表示 1-12 月
			var month = date.getMonth();
			console.log(month);

			// 获取天
			var day = date.getDate();
			console.log(day);

			// 获取小时
			var hour = date.getHours();
			console.log(hour);

			// 获取分钟
			var minute = date.getMinutes();
			console.log(minute);

			// 获取秒数
			var second = date.getSeconds();
			console.log(second);
```

#### 		随机笑话

​				输入3，随机给我讲个笑话
​				随机值：每次给你的值，一般情况下是不一样的
​				有给随机值的一个对象Math

```js
				// 获取随机数
				var r = Math.random();

				// 输出一个在 [0,1) 之间的浮点数，可以得到0，但是无法得到1
				console.log(r); 
```

​				如果想要得到一个随机整数，需要把整机浮点数  乘以 一个 倍数，再取整，

```js
				// 获取 [0,10) 之间的随机浮点数，随机的一个值，
				var r = Math.random() * 10;
```

​				取整：向下取整，向数轴的左边获取最近的一个整数

```js
				// 向下取整
				var a = Math.floor(1.12);
				console.log(a); // 输出1
				var b = Math.floor(1.99);
				console.log(b); // 输出1
				var c = Math.floor(-3.2);
				console.log(c); // 输出 -4
				var d = Math.floor(3.9);
				console.log(d); // 输出 -4
```

​				获取一个随机整数

```js
				// 获取一个 [0,10] 之间的随机整数
				var r = Math.random();
				r = r * (10 + 1) ;
				// 因为 Math.random得到的是不能得到1的浮点数，我们等下要向下取整，就得不到10了， * 				11 向下取整才能得到10
				r = Math.floor(r);
				console.log(r); // 得到一个在 [0,10] 之间的整数
```

​				分析：随机来个笑话：

​					笑话是个数字，有很多效果，我不知道要哪个；

​					随机给我来一个，随机的下标就可以；

​					随机的下标：随机的整数；看整数的范围：数组的长度；

```js
				var index = Math.random();  // [0,1)
				index *= list.length ; // [0,5)

				// 最后一条永远拿不到，让最后一个笑话为空；
				index = Math.floor(index); // [0,4]
```