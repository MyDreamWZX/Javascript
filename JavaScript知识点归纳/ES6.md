# 变量声明
```
<!DOCTYPE html>
<html lang="zh-cn">
	<head>
		<meta http-equiv="Content-Type" content="text/html; charset=utf-8" />
        <title></title>
		<style>
			
		</style> 
		<script>

			/*
				var 声明变量

				let 
					1. 不能重复声明变量


				const
			*/

			var asd = 1;
			var asd = 2;

			let ketang = 10;
			let ketang = 20;

			console.log(ketang);



		</script>
	</head>

	<body>
		
	</body>
</html>
```
```
<!DOCTYPE html>
<html lang="zh-cn">
	<head>
		<meta http-equiv="Content-Type" content="text/html; charset=utf-8" />
        <title></title>
		<style>
			
		</style>
		<script>

			/*
				var 声明变量

				let 
					1. 不能重复声明变量
					2. let不存在变量提升，必须声明后才使用


				const
			*/
			console.log(asd);
			var asd = 1;
			console.log(ketang);
			let ketang = 10;

			console.log(ketang);



		</script>
	</head>

	<body>
		
	</body>
</html>
```
```
<!DOCTYPE html>
<html lang="zh-cn">
	<head>
		<meta http-equiv="Content-Type" content="text/html; charset=utf-8" />
        <title></title>
		<style>
			
		</style>
		<script>

			/*
				var 声明变量

				let 
					1. 不能重复声明变量
					2. let不存在变量提升，必须声明后才使用
					3. 使用let会形成块级作用域

				const

				块级作用域
					一对大括号形成的作用域
			*/

			if(true){
				// 变量提升，会把变量名提升，if走不进来没赋值
				var asd = 123;

				// 在这个if中使用，会形成块级作用域
				let ketang = 10;
				console.log(ketang);
			}

			console.log(asd);
			console.log(ketang);



		</script>
	</head>

	<body>
		
	</body>
</html>
```
```
<!DOCTYPE html>
<html lang="zh-cn">
	<head>
		<meta http-equiv="Content-Type" content="text/html; charset=utf-8" />
        <title></title>
		<style>
			
		</style>
		<script>

			/*
				var 声明变量

				let 
					1. 不能重复声明变量
					2. let不存在变量提升，必须声明后才使用
					3. 使用let会形成块级作用域

				const

				块级作用域
					一对大括号形成的作用域
			*/

			
			for( let i = 0; i < 10; i++ ){
				console.log(i);
			}
			// 在for循环中用let声明了变量，在外面不能使用
			console.log(i);



		</script>
	</head>

	<body>
		
	</body>
</html>
```
```
<!DOCTYPE html>
<html lang="zh-cn">
	<head>
		<meta http-equiv="Content-Type" content="text/html; charset=utf-8" />
        <title></title>
		<style>
			
		</style>
		<script>

			/*
				var 声明变量

				let 
					1. 不能重复声明变量
					2. let不存在变量提升，必须声明后才使用
					3. 使用let会形成块级作用域

				const
					声明常量

				块级作用域
					一对大括号形成的作用域
			*/

			window.onload = function(){
				var lis = list.querySelectorAll("li");
				/*
					父级作用域
						for( let i = 0; i < lis.length; i++ )
					子级作用域
						{
							lis[i].onclick = function (){
								console.log(i);	
							}
						}

					每次执行，都会重新声明一个变量i

					没声明这个i，初始值是上一次执行的结果
				*/
				for( let i = 0; i < lis.length; i++ ){
					console.log(i);
					lis[i].onclick = function (){
						console.log(i);	
					}
				}

				/*for( var i = 0; i < lis.length; i++ ){
					(function (i){
						lis[i].onclick = function (){
							console.log(i);	
						}
					})(i);
				}*/
			};


		</script>
	</head>

	<body>
		<ul id="list">
			<li>123</li>
			<li>123</li>
			<li>123</li>
			<li>123</li>
		</ul>
	</body>
</html>
```
```
<!DOCTYPE html>
<html lang="zh-cn">
	<head>
		<meta http-equiv="Content-Type" content="text/html; charset=utf-8" />
        <title></title>
		<style>
			
		</style>
		<script>

			/*
				var 声明变量

				let 
					1. 不能重复声明变量
					2. let不存在变量提升，必须声明后才使用
					3. 使用let会形成块级作用域

				const
					声明常量
						一但定义了值不能改变

				块级作用域
					一对大括号形成的作用域
			*/

			
			let asd = 123;

			asd = 10;

			
			const ketang = 20;

			//ketang = 30;  // 使用const声明的变量，不能再次赋值，否则会报错

			console.log(asd);
			console.log(ketang);


		</script>
	</head>

	<body>
		<ul id="list">
			<li>123</li>
			<li>123</li>
			<li>123</li>
			<li>123</li>
		</ul>
	</body>
</html>
```
```
<!DOCTYPE html>
<html lang="zh-cn">
	<head>
		<meta http-equiv="Content-Type" content="text/html; charset=utf-8" />
        <title></title>
		<style>
			
		</style>
		<script>

			/*
				var 声明变量

				let 
					1. 不能重复声明变量
					2. let不存在变量提升，必须声明后才使用
					3. 使用let会形成块级作用域

				const
					声明常量
						一但定义了值不能改变

				块级作用域
					一对大括号形成的作用域
			*/

			// 引用类型  引用的地址
			
			const ketang = [1,2,3];  // 赋址

			ketang.push(10); // 引用的数组可以改变

			//ketang = 123; // 变量的值不能改正

			console.log(ketang);



		</script>
	</head>

	<body>
		<ul id="list">
			<li>123</li>
			<li>123</li>
			<li>123</li>
			<li>123</li>
		</ul>
	</body>
</html>
```
```
<!DOCTYPE html>
<html lang="zh-cn">
	<head>
		<meta http-equiv="Content-Type" content="text/html; charset=utf-8" />
        <title></title>
		<style>
			
		</style>
		<script>

			/*
				var 声明变量

				let 
					1. 不能重复声明变量
					2. let不存在变量提升，必须声明后才使用
					3. 使用let会形成块级作用域

				const
					声明常量
						一但定义了值不能改变

				块级作用域
					一对大括号形成的作用域
			*/

			// 引用类型  引用的地址
			
			const ketang = {
				a:10
			}

			ketang.a  =20;

			console.log(ketang);


		</script>
	</head>

	<body>
		<ul id="list">
			<li>123</li>
			<li>123</li>
			<li>123</li>
			<li>123</li>
		</ul>
	</body>
</html>
```
# defineProperty
```
<!DOCTYPE html>
<html lang="zh-cn">
	<head>
		<meta http-equiv="Content-Type" content="text/html; charset=utf-8" />
        <title></title>
		<style>
			
		</style>
		<script>

			/*
				Object.defineProperty() 方法会直接在一个对象上定义一个新属性，或者修改一个对象的现有属性， 并返回这个对象

				Object.defineProperty(obj, prop, descriptor)
			*/

			// 当给一个对象定义一个属性的时候，能不能对这个属性进行一些描述
			/*
				属性值是什么  value
				属性值能不能重新改写  writable
			*/

			var obj = {
				a:1
			};

            Object.defineProperty(obj,'ketang',{
            	value:'123',    // 属性对应的值 默认为undefined
            	writable:true,	// 是否可被改写，true，可以，false不可以，默认为false
            	enumerable: true // 是否可被枚举 true，可以，false不可以，默认为false
            });

			obj.ketang = '我被改了';

			for(var attr in obj){
				console.log(attr);
			}

			console.log(obj);

			// 定义添加属性
			/*obj.asd = 10;
			obj.asd = 30;*/


		</script>
	</head>

	<body>
		<ul id="list">
			<li>123</li>
			<li>123</li>
			<li>123</li>
			<li>123</li>
		</ul>
	</body>
</html>
```
# 变量解构赋值
```
<!DOCTYPE html>
<html lang="zh-cn">
	<head>
		<meta http-equiv="Content-Type" content="text/html; charset=utf-8" />
        <title></title>
		<style>
			
		</style>
		<script>
			// ES6 允许按照一定模式，从数组和对象中提取值，对变量进行赋值，这被称为解构（Destructuring）。
			
			let arr = [[1,2],[3,4],[5,6]];

			// 数组中每个新数组两个值相加的和放在新数组中

			/*let a = arr.map(function ([a,b]){
				return a+b;
			});

			console.log(a);*/

			let str = 'asdvketang';

			let a1 = str[0];

			let [a,b,c] = str;

			console.log(a,b,c);



		</script>
	</head>

	<body>
		
	</body>
</html>
```
# 函数扩展
```
<!DOCTYPE html>
<html lang="zh-cn">
	<head>
		<meta http-equiv="Content-Type" content="text/html; charset=utf-8" />
        <title></title>
		<style>
			
		</style>
		<script>
			
			

		</script>
	</head>

	<body>
		<input type="button" value="改变了" />
		<input type="button" value="改变了" />
		<input type="button" value="改变了" />
		<script>
			var btns = document.getElementsByTagName("input");
			for( var i = 0; i < btns.length; i++ ){
				btns[i].onclick = function (){
					/*let that = this;
					setTimeout(function (){
						// 给btn变颜色
						that.style.background = 'red';
					},1000)	*/	
					// 点击之后，函数调用了call方法，立马把函数执行了
					setTimeout(function (){
						// 给btn变颜色
						this.style.background = 'red';
					}.call(this),1000000)
				};
			}
		</script>
	</body>
</html>
```
```
<!DOCTYPE html>
<html lang="zh-cn">
	<head>
		<meta http-equiv="Content-Type" content="text/html; charset=utf-8" />
        <title></title>
		<style>
			
		</style>
		<script>
			
			

		</script>
	</head>

	<body>
		<input type="button" value="改变了" />
		<input type="button" value="改变了" />
		<input type="button" value="改变了" />
		<script>

			/*
				箭头函数
				() => {}
			*/

			let func = (a) => {return a};

			console.log(func(1));


			var btns = document.getElementsByTagName("input");
			for( var i = 0; i < btns.length; i++ ){
				btns[i].onclick = function (){

					setTimeout(()=>{
						console.log(this);
						this.style.background = 'red';
					},1000)
				};
			}
		</script>
	</body>
</html>
```
# 箭头函数
箭头函数

1. 函数体内的this对象，就是定义时所在的对象，而不是使用时所在的对象。
2. 
2. 不可以使用arguments对象，该对象在函数体内不存在

rest参数
...变量名

用于获取函数的多余参数，这样就不需要使用arguments对象了。

rest 参数搭配的变量是一个数组，该变量将多余的参数放入数组中。
```
<!DOCTYPE html>
<html lang="zh-cn">
	<head>
		<meta http-equiv="Content-Type" content="text/html; charset=utf-8" />
        <title></title>
		<style>
			
		</style>
		<script>
			/*
				定义函数 箭头函数
					=>

			*/

			document.onclick  = function (){
				setTimeout(function (){
					console.log(this);	
				},1000);
				// 箭头函数中的this，是在定义时候拥有定义作用域的this
				setTimeout(() => {
					console.log(this);	
				},1000);
			};

			


		</script>
	</head>

	<body>
		
	</body>
</html>
```
# this
```
<!DOCTYPE html>
<html lang="zh-cn">
	<head>
		<meta http-equiv="Content-Type" content="text/html; charset=utf-8" />
        <title></title>
		<style>
			
		</style>
		<script>
			var a = 10;
			var obj = {
				a:1,
				fn:function (){
					console.log(this.a);	
				}
			}

			obj.fn();  // 函数是obj调用的，函数中this就指向obj

			// 把属性对应的函数赋值给了变量f，调用f就是直接调用，f中函数执行widown
			var f = obj.fn;
			f();


		</script>
	</head>

	<body>
		
	</body>
</html>
```
```
<!DOCTYPE html>
<html lang="zh-cn">
	<head>
		<meta http-equiv="Content-Type" content="text/html; charset=utf-8" />
        <title></title>
		<style>
			
		</style>
		<script>
			var a = 10;
			var obj = {
				a:1,
				fn: () => {  // 箭头函数拥有包含这个箭头函数的作用的this
					console.log(this);
					console.log(this.a);	
				}
			}

			obj.fn(); 
			var f = obj.fn;
			f();


		</script>
	</head>

	<body>
		
	</body>
</html>
```
# 展开运算符
```
<!DOCTYPE html>
<html lang="zh-cn">
	<head>
		<meta http-equiv="Content-Type" content="text/html; charset=utf-8" />
        <title></title>
		<style>
			
		</style>
		<script>
			
			
			/*
				...数组
					展开运算符
			*/

			let arr1 = [1,2,3];
			let arr2 = [4,5,6];

			let arr3 = [...arr1,...arr2];

			console.log(arr3);

			// 数组，求数组中最大的值 Math.max

			var arr = [9,4,1,8,10,40,0];

			console.log(...arr);

			console.log(Math.max(...arr));


		</script>
	</head>

	<body>
		
	</body>
</html>
```
# 暂时性死区
```
<!DOCTYPE html>
<html lang="zh-cn">
	<head>
		<meta http-equiv="Content-Type" content="text/html; charset=utf-8" />
        <title></title>
		<style>
			
		</style>
		<script>
			/*function fn(a=10){ 
				//let a = 30;
				console.log(a);
			}

			fn(0);
			var n = 20;
			let n = 10;
			

			console.log(n);*/

		</script>
	</head>

	<body>
		<script>
			
			
			console.log(window.n);  // 不报错
			console.log( typeof n );

			//var n;  // 排除定义未赋值 

			// 判断变量有没有定义
			if( typeof n !== 'undefined' ){
				console.log('定义了');
			}else{
				console.log("没定义");
			}

			// 总之，在代码块内，使用let命令声明变量之前，该变量都是不可用的。这在语法上，称为“暂时性死区”（temporal dead zone，简称 TDZ）。

			console.log(typeof m);
			let m = 10;


		</script>
	</body>
</html>
```
# 传参
```
<!DOCTYPE html>
<html lang="zh-cn">
	<head>
		<meta http-equiv="Content-Type" content="text/html; charset=utf-8" />
        <title></title>
		<style>
			
		</style>
		<script>
			function fn(a=10){ 
				let a = 30;  // 不能使用let声明，可以使用var声明
				console.log(a);
			}

			fn(0);
			

			/*{
				var a = 10;
				var a = 30;
				console.log(a);
			}*/

		</script>
	</head>

	<body>
		<script>



		</script>
	</body>
</html>
```
# 绑定this
```
<!DOCTYPE html>
<html lang="zh-cn">
	<head>
		<meta http-equiv="Content-Type" content="text/html; charset=utf-8" />
        <title></title>
		<style>
			
		</style>
		<script>
			// 绑定this 就是把函数中this指向指定的值
			/*
				立马执行了：
					函数.call()
					函数.apply()
				不执行函数，改this值
					函数.bind();
			*/

			document.onclick  =function (){
				function fn(){
					console.log("我被执行了");	
					console.log(this);	
				}
				// 会返回新的函数
				let f = fn.bind(this)

				setTimeout(f,1000)	
			};		

		</script>
	</head>

	<body>
		<script>



		</script>
	</body>
</html>
```
# 模板字符串
```
<!DOCTYPE html>
<html lang="zh-cn">
	<head>
		<meta http-equiv="Content-Type" content="text/html; charset=utf-8" />
        <title></title>
		<style>
			
		</style>
		<script>
			let a = 'ketang';
			let str = `<li>${a}</li>`;

			console.log(str);

			// 模板引擎

			/*var template = `
			<ul>
			  <% for(var i=0; i < data.supplies.length; i++) { %>
			    <li><%= data.supplies[i] %></li>
			  <% } %>
			</ul>
			`;*/
		</script>
	</head>

	<body>
		
	</body>
</html>
```
# 数值扩展
```
<!DOCTYPE html>
<html lang="zh-cn">
	<head>
		<meta http-equiv="Content-Type" content="text/html; charset=utf-8" />
        <title></title>
		<style>
			
		</style>
		<script>
			parseInt(0.1);

			// 模块化

			console.dir(Number);

			Number.parseInt('100px')
			Number.parseFloat('100px')
			Number.isNaN('100px')

		</script>
	</head>

	<body>
		
	</body>
</html>
```
```
<!DOCTYPE html>
<html lang="zh-cn">
	<head>
		<meta http-equiv="Content-Type" content="text/html; charset=utf-8" />
        <title></title>
		<style>
			
		</style>
		<script>

			var arr = [1,2,3];
			
			console.log(arr);
			/*var arr2 = new Array();
			//1. 使用下标添加值 或者push
			arr2[0] = 'm';
			arr2[1] = 'v';*/
			//var arr2 = new Array('asd','ket');
			//var arr2 = new Array(3);  // 代表的是数组的length为3
			//var arr2 = Array.of(3);
			var arr2 = Array.of(3,4,5,6,7,8);
			console.log(arr2);


		</script>
	</head>

	<body>
		
	</body>
</html>
```
# Array.from
```
<!DOCTYPE html>
<html lang="zh-cn">
	<head>
		<meta http-equiv="Content-Type" content="text/html; charset=utf-8" />
        <title></title>
		<style>
			
		</style>
		<script>

			


		</script>
	</head>

	<body>
		<ul>
			<li>123</li>
			<li>123</li>
			<li>123</li>
			<li>123</li>
		</ul>
		<script>
			let lis = document.getElementsByTagName("li");
			// [li,li,li]

			// 把li中内容放在一个数组中
			/*
				语法
					Array.from(数组类数组[,callback,改变callback中this的指向])
			*/

			let newArr = Array.from(lis,function (node){
				console.log(this);
				return node.innerHTML;
			},[1,2,3]);

			console.log(newArr);


		</script>
	</body>
</html>
```
# find
```
<!DOCTYPE html>
<html lang="zh-cn">
	<head>
		<meta http-equiv="Content-Type" content="text/html; charset=utf-8" />
        <title></title>
		<style>
			
		</style>
		<script>

			


		</script>
	</head>

	<body>
		<ul>
			<li>123</li>
			<li>123</li>
			<li>123</li>
			<li>123</li>
		</ul>
		<script>
			
			let arr = [1,2,3,4,5,6];

			// 找到数组中小于的5的数有没有
			let newArr = arr.find(function (item,index,arr){
				// 找到符合数组中首次符合条件的
				return item < 1
			});

			console.log(arr);
			console.log(newArr);


		</script>
	</body>
</html>
```
# for of
```
<!DOCTYPE html>
<html lang="zh-cn">
	<head>
		<meta http-equiv="Content-Type" content="text/html; charset=utf-8" />
        <title></title>
		<style>
			
		</style>
		<script>

			


		</script>
	</head>

	<body>
		<ul>
			<li>123</li>
			<li>123</li>
			<li>123</li>
			<li>123</li>
		</ul>
		<script>
			/*
				for of
				 	直接循环出value值
				 for in
				 	循环的是key值
			*/

			let arr = ["m","v","c"];

			// 遍历器结构
			for( let value of arr ){
				console.log(value);
			}



			for(let attr in arr){
				console.log(attr);
			}


		</script>
	</body>
</html>
```
# includes
```
<!DOCTYPE html>
<html lang="zh-cn">
	<head>
		<meta http-equiv="Content-Type" content="text/html; charset=utf-8" />
        <title></title>
		<style>
			
		</style>
		<script>

			


		</script>
	</head>

	<body>
		<ul>
			<li>123</li>
			<li>123</li>
			<li>123</li>
			<li>123</li>
		</ul>
		<script>
			
			var arr = [NaN,1,2,3,4];

			console.log(arr.indexOf(NaN));
			console.log(arr.indexOf(1));
			// 判断数组中有没有指定的值，NaN也可以判断出来
			// 第二个参数，开始搜索的位置
			console.log(arr.includes(NaN,3));


		</script>
	</body>
</html>
```
