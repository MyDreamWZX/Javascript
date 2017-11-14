# 好友列表

```
<!DOCTYPE html>
<html lang="en">

<head>
<meta charset="UTF-8">
<title></title>
<style type="text/css">
ul,
li {
    padding: 0;
    margin: 0;
    list-style: none;
}

.box {
    width: 1000px;
    height: 800px;
    background-image: url(bg.png);
    margin: 0 auto;
}

.phone {
    width: 384px;
    height: 707px;
    margin: 0 auto;
    background-image: url(bg1.png);
    background-repeat: no-repeat;
    box-sizing: border-box;
    padding: 72px 50px 0 43px;
}

a {
    height: 50px;
    display: block;
    background-color: rgba(0, 0, 0, 0.65);
    text-decoration: none;
    color: #fff;
    line-height: 50px;
    padding-left: 20px;
}

li {
    background-color: #000;
    height: 50px;
    display: block;
    color: #fff;
    padding-left: 30px;
    line-height: 50px;
    cursor: pointer;
}

.one,
.two,
.three {
    margin-bottom: 10px;
}

ul {
    display: none;
}

.gary {
    background: #404040;
}

.active {
    background: #7b2c2c;
}
</style>
</head>

<body>
<div class="box">
    <div class="phone">
        <div class="one divs">
            <a href="#">我的好友</a>
            <ul class="uls">
                <li>张一</li>
                <li>张二</li>
                <li>张三</li>
                <li>张四</li>
            </ul>
        </div>
        <div class="two divs">
            <a href="#">企业好友</a>
            <ul class="uls">
                <li>张五</li>
                <li>张六</li>
                <li>张七</li>
            </ul>
        </div>
        <div class="three divs">
            <a href="#">黑名单</a>
            <ul class="uls">
                <li>张八</li>
                <li>张九</li>
            </ul>
        </div>
    </div>
</div>
<script>
var aS = document.querySelectorAll('.divs a');
uls = document.querySelectorAll('.divs .uls');
flag = 0;//初始化a的下标值
lis = document.querySelectorAll(".uls li");
isClick = false;
flagIndex = 0;

for (var i = 0; i < aS.length; i++) {
    aS[i].index = i; //初始化下标值
    aS[i].display = 'none'; //自定义display
    aS[i].onclick = function() {

        lis[flagIndex].style.background = ''; //去除上次li的背景色
        lis[flagIndex].isClick = false; //上次点击li为false

        if (flag == this.index) {//如果flag的下标等于当前a的下标

        } else if (flag != this.index) { //如果flag的下标不等于当前a的下标
            aS[flag].className = '';//取消a的背景色
            uls[flag].style.display = 'none';//取消ul的display
            aS[flag].display = 'none';//a的自定义为display是none
        }


        if (this.display == 'none') {//如果a的自定义display是none
            uls[this.index].style.display = 'block';//对应的ul为block
            this.className = 'active'//为此a添加背景色
            this.display = 'block';//为此a的display为block
        } else {//如果a自定义display是block
            uls[this.index].style.display = 'none';//对应的ul为none
            this.display = 'none';//为此a的display为none
            this.className = '';//取消此a的class
        }

        flag = this.index;//让自定义值等于当前点击的下标值
    };
}

for (var i = 0; i < lis.length; i++) {
    lis[i].isClick = false;//初始化li为没点击
    lis[i].index = i;//初始化li下标值
    lis[i].onmouseover = function() {//鼠标经过li
        if (this.isClick) {//如果为false

        } else if (!this.isClick) {//如果为true
            this.style.background = '#ccc';
        }

    }
    lis[i].onmouseout = function() {//鼠标离开li
        if (this.isClick) {

        } else if (!this.isClick) {
            this.style.background = '';
        }
    }
    lis[i].onclick = function() {//鼠标点击li
        if (flagIndex == this.index) {//li的下标等于当前点击的下标

        } else if (flagIndex != this.index) {
            lis[flagIndex].style.background = '';
            lis[flagIndex].isClick = false;
        }
        
        this.isClick = true;
        this.style.background = '#7b2c2c';
        flagIndex = this.index;
    }
}
</script>
</body>

</html>

```
# 音乐全选

```
<!DOCTYPE html>
<html lang="en">

<head>
<meta charset="UTF-8">
<title></title>
<style type="text/css">
ul,
li {
    margin: 0;
    padding: 0;
    list-style: none;
}

.box {
    background-image: url(bg.png);
    width: 1020px;
    height: 720px;
    margin: 0 auto;
    background-repeat: no-repeat;
    background-size: cover;
}

.main {
    width: 620px;
    height: 380px;
    background-color: #fff;
    margin: 0 auto;
    position: relative;
    top: 156px;
    border-radius: 10px;
    box-shadow: 1px 1px 38px 1px;
}

.body {
    width: 100%;
    height: 310px;
    background-image: url(logo2.png);
    background-position: center center;
    background-repeat: no-repeat;
}

.footer {
    width: 100%;
    height: 70px;
    background-color: #e15671;
    border-bottom-left-radius: 10px;
    border-bottom-right-radius: 10px;
}

ul {
    width: 100%;
    position: relative;
    top: 25px;
}

li {
    width: 100%;
    height: 43px;
    line-height: 40px;
}

.singer {
    float: right;
    margin-right: 30px;
}

.song {
    margin-left: 20px;
}

label input {
    margin-left: 20px;
}

span {
    color: #000;
}

.baise {
    background-color: #fff;
}

.morense {
    background-color: #fceef1;
}

.jingguose {
    background-color: #e76a81;
}
</style>
</head>

<body>
<div class="box">
    <div class="main">
        <div class="body">
            <ul>
                <li>
                    <form>
                        <label>
                            <input type="checkbox" class="chex" />
                            <span class="song">歌曲1</span>
                            <span class="singer">歌手1</span>
                        </label>
                    </form>
                </li>
                <li>
                    <form>
                        <label>
                            <input type="checkbox" class="chex" />
                            <span class="song">歌曲2</span>
                            <span class="singer">歌手2</span>
                        </label>
                    </form>
                </li>
                <li>
                    <form>
                        <label>
                            <input type="checkbox" class="chex" />
                            <span class="song">歌曲3</span>
                            <span class="singer">歌手3</span>
                        </label>
                    </form>
                </li>
                <li>
                    <form>
                        <label>
                            <input type="checkbox" class="chex" />
                            <span class="song">歌曲4</span>
                            <span class="singer">歌手4</span>
                        </label>
                    </form>
                </li>
                <li>
                    <form>
                        <label>
                            <input type="checkbox" class="chex" />
                            <span class="song">歌曲5</span>
                            <span class="singer">歌手5</span>
                        </label>
                    </form>
                </li>
                <li>
                    <form>
                        <label>
                            <input type="checkbox" class="chex" />
                            <span class="song">歌曲6</span>
                            <span class="singer">歌手6</span>
                        </label>
                    </form>
                </li>
            </ul>
        </div>
        <div class="footer">
            <form style="line-height:70px;">
                <label>
                    <input type="checkbox" class="quanxuan" />
                    <span style="margin-left:21px;color:#fff;">全选</span>
                </label>
            </form>
        </div>
    </div>
</div>
<script type="text/javascript">
var lis = document.querySelectorAll(".body li");
var quanxuan = document.querySelector(".quanxuan");
var inputs = document.querySelectorAll(".chex");

for (var i = 0; i < lis.length; i++) {
    if (i % 2 == 0) {//奇数
        lis[i].style.background = '#fff'
    } else {//偶数
        lis[i].style.background = '#ffaebd';
    }
    lis[i].index = i;//自定义下标
    lis[i].onmouseover = function() {//鼠标经过
        this.style.background = '#e76a81';
    }
    lis[i].onmouseout = function() {//鼠标离开
        
        var inputCheckbox = this.querySelector("input");//获取每个li里的input
        if (inputCheckbox.checked) { //如果没被选中
            
        }else if(!inputCheckbox.checked){
            if (this.index % 2 == 0) {//奇数行
                this.style.background = '#fff'//白色
            } else {//偶数行
                this.style.background = '#ffaebd';//默认色
            }
        }
    }
}


quanxuan.onclick = function() {//鼠标点击
    for (var i = 0; i < inputs.length; i++) {
        inputs[i].checked = this.checked;//每个单选按钮的checked等于多选按钮的checked

        if (this.checked) {//如果全选按钮选中的话，
            lis[i].style.background = '#e76a81';//为全部li添加背景色
        } else {//如果全选按钮没选中
            if (lis[i].index % 2 == 0) {//奇数行
                lis[i].style.background = '#fff'//白色
            } else {//偶数行
                lis[i].style.background = '#ffaebd';//默认色
            }
        }
    }
}

for (var j = 0; j < inputs.length; j++) {
    inputs[j].onclick = function() {//鼠标点击
        if (this.checked) {//如果单选框被选中
            var checkedAll = true;//初始化全选框默认值
            for (var i = 0; i < inputs.length; i++) {
                if (inputs[i].checked) {//如果单选框全被选中

                } else if (!inputs[i].checked) {//如果单选框没被全选
                    checkedAll = false;//全选框为false
                    break;
                }
            }
            quanxuan.checked = checkedAll;
        } else {
            quanxuan.checked = false;
        }
    }
}
</script>
</body>

</html>

```
# 动态特性
getElementsByTagName 有动态特性
当向一个元素增加或删除元素，集合也会改变
getElementsByClassName

但是用一下两个方法的时候，要等动态添加元素之后再获取
	querySelector
	querySelectorAll
		没有动态特性

```
var list = document.getElementById("list");
// 用li
var lis = list.getElementsByTagName("li");



console.log( lis.length );  // 0

var str = '';
for( var i = 0; i < 10; i++ ){
str += '<li>123</li>'
}

list.innerHTML = str;

var lis2 = list.querySelectorAll("li");  // 不具备动态特性

console.log( lis.length );  // 10

console.log(lis2.length);
```
# 数据类型

```
/*
js数据类型：
两大类型：
基本（简单）数据类型
复合（引用）数据类型

基本（简单）数据类型
String => 字符串
	值：一对单引号或双引号包含的0个或多个字符串组成串
	"" 空字符串
	''
	'abc'

Number => 数字
	整数
	浮点数
		0 1 2 3 4....
	取值范围：
		正无穷大 +Infinity
		负无穷大 -Infinity

Boolean => 布尔值
	值： true false
Undefined => 未定义
	值：undefined
		1. 定义一个变量没赋值，默认的值为undefined
		2. 找一个对象上不存在的属性，返回undefined

Null  => 空
	值：null
		声明变量不确定要赋的值，可以使用null来占位

复合（引用）数据类型
Object => 对象

值:是由0个或多个名/值组成的集合
		


内置的函数
字符串 String
数字 Number
布尔值 Boolean

对象 Object

内置的函数，会打印function 函数名() { [native code] }
	*/
```
# typeof 检测数据类型

```
检测数据的类型
	一元运算符 typeof

	使用： typeof 数据

	typeof运算之后会返回一个字符串，这个字符串来表示数据的属于的类型

	typeof 数据 运算数据之后，可以得到以下字符串：
		string
		number
		boolean
		undefined
		object
		function

	数组和函数都属于对象的
		函数是可执行的一种对象，比较特殊
		js中函数属于一等公民

	注意：使用typeof检测null，返回的是object这个字符串

+ 二元运算符
三元运算符 条件 ? 条件成立走这里 : 条件不成立走这里
```
# 数据类型转换

```
数据类型转换：把一种数据的类型转成另一种类型

把数据转成三种类型：
	Number
	String
	Boolean

转成数字类型：
	Number(要转的数据)
		true => 1
		false => 0
		纯数字的字符串 => 转对应的数字
		undefined => NaN
		null => 0
		NaN => Not a Number 数字类型
			调用Number之后，不能转对应的数字，会用NaN来表示
			运算失败后，会用NaN表示
			和任何值比较都不相同，包括自己比较也不相同
			和任何值比较都返回false
		检测一个值是不是NaN
			可以使用NaN自己和自己不相同这个规则来比较
			isNaN(值)
				值是NaN，返回true
				值不是NaN，返回false
	parseInt(要转的数据) 得到的是整数
		要转的数据遇到不是数字的就返回数字部分
		数据的第一位不是数字，返回NaN
	parseFloat(要转的数据) 得到的是小数
备注：
	函数 => 方法
```
# isNaN
检测一个值是不是NaN
	isNaN(要检测的值)
		值为NaN 返回就是true
		值不为NaN 返回的是false

	会先调用Number方法转成数字类型

每一个函数执行了都会有结果
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
	/*
		字符串

			'' 一对
			"" 
		es6提供的
			`` 反引号 模板字符串（超级字符串）

			要渲染提供的数据，
				${数据}

		\ 传义符

		html结构有时候也称之为模板

		备注：
			字符串一旦定义，不能更改

	*/

	var strTest = 'aaaketang'; // 赋值

	strTest = 'abc';//改的不是字符串，而是变量存的值

	strTest[0] = "w";
	console.log( strTest );


	
	var arr = [1,2,3,4];  // 赋址
	arr[0] = 'w';  // 改变了数组的第一位
	console.log( arr );

</script>
</head>

<body>
<div class="box">
	<!-- <h2>大标题</h2>
	<span>小标题</span>
	<ul>
		<li>122</li>
		<li>122</li>
		<li>122</li>
		<li>122</li>
	</ul> -->
</div>
<script>
	var box = document.querySelector(".box");


	var title1 = '这是大标题'
	var title2 = '标题'

	var arr = [1,2,3,43,5];

	var str = `
		<h2>${title1}</h2>
		<span>${title2}</span>
	`
	var str2 = '<ul>';
		for( var i = 0; i < arr.length; i++ ){
			str2 += `<li>${arr[i]}</li>`;
		}
	str2 += "</ul>"

	box.innerHTML = str + str2;


</script>
</body>
</html>
```
# 运算符
算术运算符
+ 加、- 减、* 乘、/ 除、% 取模（求余数）、++、--
赋值运算符
=、+=、-=、*=、/=、%=
关系运算符
<、>、<=、>=、==、!=、===、!==
比较后都会返回布尔值

	== 
		会把等号两边的值隐式转换，转成同一种类型的
			数字和字符串比较时候，字符串转成数字
		转成相同类型后，比较值是否相同
	===
		先比较类型，不相同返回false
		类型相同，比较值

	!= 不等于
	!== 不全等于
逻辑运算符	
&& 与、并且
	左右两边的条件要同时满足才可以
|| 或、
	左右两边的条件只需要满足其一就可以

! 否 、
三目运算符
判断条件 ? 条件为true执行这里代码 : 条件为false执行这里代码

条件为true，返回?后面的值
条件为false，返回:后面值

不要嵌套太多三目
优先级：
https://developer.mozilla.org/zh-CN/docs/Web/JavaScript/Reference/Operators/Operator_Precedence

结合性：
相同等级的运算符同时出现，有一个结合性来决定是从左向右元素还是从右向左运算
# 求数组中最大值

```
var arr = [1,3,600,100,50,-40,300];

// 找出这个一堆数字中最大的值
// 用一个变量先记录一个值，拿这个变量去跟数组中每一个元素对比，如果数组中这个数大于了变量记录的值，把这个数给到变量；

var n = arr[0]; // n = 1

for( var i = 1; i < arr.length; i++ ){
	// arr[i] 3 600 100
	// n 1 3 600  600
	if( arr[i] > n ){
		n = arr[i]
	}
}

console.log(n);
```
# 数据类型
数据类型：

Number、
String、
Boolean、
Undefined Null Object
typeof 数据;
运算之后，返回数据的类型使用字符串表示
	'number'
	'string'
	'boolean'
	'object'
	'undefined'
	'function'

typeof(数据) 不建议这样使用，误以为这是一个函数
# NaN
NaN
not a Number
数字类型
不和任何值相等，包括自身
和任何一个值元素，都会得到NaN
和任意值比较，都是false
isNaN(值)
检测值是不是NaN
	是 true
	不是 false

- * / % 只能做运算
两边是数字，不是数字要转成数字
```
/*
console.log( Number('abc') ); //NaN

console.log( {a:1} - 1 );

console.log( "abc" - 1 );  //NaN

console.log( NaN );

console.log( NaN == NaN );*/

var n = "a"+1;

console.log( isNaN('abc'-1) );
console.log( isNaN(parseInt("a100px")) );


if( n > 1 ){
	alert("通过")
}

var arr = [1+1,2+2, "abc"-1];
// [0:1+1]
//arr[0] = 1+1
console.log( arr[0] );  // 得到运算后的值

console.log( arr );
var k = 2;
var a = k;

// [var, a,=,k]
var abc = 2;
var abc = 1;
```
# 函数
函数
可存放多行代码，形成代码块
是一个对象，可执行的对象
可以作为值使用
使用关键字 function
语法：
function [函数名](){

}
完整写法：
function [函数名]([参数1,参数2,。。。。]){
	// 函数体 代码块
	[return 值]
}
函数定义：
函数声明
	function 函数名(){

}
注意：函数声明必须带上函数名
函数表达式
把函数作为值使用，赋值为变量
var fn = function (){

}
函数调用
函数定义后，不会执行函数中的代码，只能调用才能执行
调用：函数名()
调用位置：
函数声明调用：
	可以在函数声明之前和之后都可以调用
函数表达式调用：
	必须在赋值之后调用

函数参数
在函数共用的时候，在调用函数的时候要执行不同的值，通过传参的形式解决

形参
函数定义的时候，写在小括号中
function func([形参1,形参2]){

}
形参的命名规则，要符合变量的命名规则
形参就是在函数的内部声明的变量,默认值为undefined
形参只能在函数中使用
实参
在调用函数时，写在小括号中
会把这个实参赋值给形参

形参和实参是一一对应的，以逗号隔开
# 函数参数例子

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
<div class="box">
	<input type="" name="">
	<input type="button" value="得到value值" />
	<span>0</span>
</div>
<div class="box2">
	<input type="" name="">
	<input type="button" value="得到value值" />
	<span>0</span>
</div>
 <div class="box3">
	<input type="" name="">
	<input type="button" value="得到value值" />
	<span>0</span>
</div>
<!--<div>
	<input type="" name="">
	<input type="button" value="得到value值" />
	<span>0</span>
</div>
<div>
	<input type="" name="">
	<input type="button" value="得到value值" />
	<span>0</span>
</div>
<div>
	<input type="" name="">
	<input type="button" value="得到value值" />
	<span>0</span>
</div> -->

<script>
	getValue(".box")
	getValue(".box2")
	getValue(".box3")

	function getValue(classNames){
		var box = document.querySelector(classNames);
		var inputs = box.querySelectorAll("input");
		var span = box.querySelector("span");
		inputs[1].onclick = function (){
			span.innerHTML = inputs[0].value;	
		}	
	}

</script>

</body>
</html>
```
# 文本框默认选中

```
// select选中文本框中的值
	btn.onclick  = function (){
		message.select();	
	}
```
# arguments

```
<!DOCTYPE html>
<html lang="zh-cn">
<head>
<meta http-equiv="Content-Type" content="text/html; charset=utf-8" />
<title></title>
<style>
	
</style>
<script>
	// 函数定义 函数声明 函数表达式
	// 函数调用 直接调用 触发事件调用
	// 参数 形参 实参

	/*
		实参的个数不固定，不确定的时候
		使用函数内部内置的变量：
			arguments 是函数实参的集合 类数组（类人猿）

			和数组有一些相同的特性，不具备数组的全部的特性
			相同特性：
				结构 []
				length
				下标
			不相同：
				类数组没有数组的方法


	*/

	var  arr = [];

	arr.push(1)

	console.log( arr.push );


	// 这个函数的作用：把传过来的参数相加
	function add(a,b){
		console.log( arguments );	// 实参的集合
		console.log(arguments.push);
		var n = 0;
		for( var i = 0; i < arguments.length; i++ ){
			n += arguments[i]
		}

		console.log(n);
	}

	add(1,2,3)
	add(3,4,3)
	add(300,4)

</script>
</head>

<body>

</body>
</html>
```
# return
2.使用关键字return
a. 只能在函数中使用
b. 函数调用后返回return后面的值
	如果return后没有值，函数返回值为undefined
c. return之后的代码停止执行

```
window.onload = function(){
	btn.onclick = function (){
		/*if(message.value == ''){
			alert("请输入内容")
		}else{
			alert("恭喜通过")
		}*/	

		if(message.value === ''){
			alert("请输入内容")
			return;
		}

		alert("通过")
	};
};	
```


# 获取计算后的样式值

```
<input type="button" value="按钮" id="btn" />
<div id="box">
	123
</div>
<script>

	/*
		获取计算后的样式
			全局函数：
				getComputedStyle()
			参数：
				是一个要获取计算后样式的元素
					getComputedStyle(元素)
			函数会返回一个对象
				对象是这个元素所有计算后的样式
	*/

	var button = document.getElementById("btn");
	var box = document.getElementById("box");



// css 可以设置也可以获取指定元素的样式
function css(element,prop,value){
	// 判断argumnets的length
	if(arguments.length>2){
		// 设置
		element.style[prop] = value;
	}else{
		// 获取
		return parseFloat(getComputedStyle(element)[prop]);
	}
}

/*console.log(css(box, "width"));;  // 获取
css(box, "height", '900px');  // 设置*/

// 每点页面一次，让div在自己width基础上增加100


document.onclick = function (){
	// 现获取到点击后box的width值
	var w = css(box, "width");
	css(box,"width", (w + 100) + 'px')	
}

</script>
```
# 小总结
数据类型：数字类型，字符串类型，布尔值，未定义、空、对象
内置的函数：Number、String、Boolean、Object
Undefined、Null（没有内置函数）
检测数据类型 typeof
'number'、'string'、'boolean'、'object'、'undefined'、'function'
数据类型转换：
转成三类：数字类型，字符串类型，布尔值

转成数字类型：
Number()
parseInt()
parseFloat()

转不成数字：NaN
数字类型
不和任何值相等、包括在自身
参与运算是NaN
比较都是false
isNaN()
转成字符串
String()
数据.toString()方法

数据+""

模板字符串/超级字符串
`` 
`
<p>${变量}</p>
`
转成布尔值
Boolean()
转成false=> '' 0 null undefined NaN 

显式类型转换
调用函数把一种类型转成另一种类型
隐式类型转换
解析器会把一种类型转成另一种类型，方便运算

+ - * / % += -=

> <

作业：验证QQ

周三：

运算符：
算术运算符
关系运算符
==
===
!=
!==
赋值运算符
= += -= 
逻辑运算符
&&
|| 
!
?:

1 < 2 ? aert(1) : null;

作业：找数据

周四：
函数定义
函数调用
函数参数


