# 匿名函数
匿名函数，立马使用，不会报错

立即让这个匿名函数执行
```
var a = function (){
	console.log("我被执行了");	
}();

(function (){
	console.log("我执行了");	
})()
console.log( +'a' );

// 尽可能少的定义全局变量，否则会造成全局变量污染

// 闭包 模块化

// A同学

(function (){
		
	var miaov = 'ketang';
	var a = 10;
	var b = 20;
	document.onclick = function (){
		console.log(miaov);	
	};
})();



// B同学
(function (){
	var miaov = 'leo';
	console.log( miaov );
})();
```
# 查找标识符

```
// 查找标识符是在定义函数的位置开始查找，不是在调用的位置查找

var a = 10;
function func(){
	console.log(a);
}

document.onclick = function (){
	var a  = 1000;
	func();	
};

function miaov(){
	var b = 0;

	function ketang(){
		b++;
		console.log(b);
	}
	

	return ketang;
}
var b = 20;
var f = miaov();

f()
f();
```
# eval

```
<textarea id="code"></textarea>
<input type="button" id="btn" value="运行代码" />
<script>
	btn.onclick = function (){
		//eval(code.value)  // 字符串 解析成代码运行	
	}
</script>
```
# 封装$

```
function $(selector,context){
//拿到第一个字符
selector = selector.trim();  // 去除前后空格

if(!context){  // 如果context没有接受任何值，contex为document
	context = document;
}

if(selector.indexOf(" ") !== -1){  // 判断是有空格，交给querySelectorAll处理
	return context.querySelectorAll(selector);
}

var firstChar = selector.charAt(0);



if(firstChar === '#'){  // id获取
	// 截取字符串一部分
	return document.getElementById(selector.slice(1));
}else if(firstChar === '.'){  // className获取
	return context.getElementsByClassName(selector.slice(1))
}else{ //tagName
	return context.getElementsByTagName(selector);
}
}


/*var list = document.getElementById("list");
var lis = list.getElementsByClassName("abc");*/

var lis = $("#list li");

console.log(lis);
```
# trim

```
/*
字符串.trim()
	去除字符串前后空格  
	
*/

var str = '        a          bc           ';

console.log( str.trim() );
```
# indexOf

```
/*
字符串.indexOf(字符串1)
作用：搜索参数字符串1在字符串中首次出现的位置  

返回值：
	搜索到指定的字符串1,返回下标
	没搜索到，返回-1
	
*/

var str = 'miaovketang';

console.log( str.indexOf("leo") );

```
# 定时器定义
定时器是什么

javaScript中系统提供的函数

定时器的作用

每隔一段时间或者延迟一段时间执行一段指定的代码

重复执行定时器

每隔一段时间就会执行第一参数传入的函数

setInterval(要执行的函数,间歇时间);

setInterval(function(){},1000,[给函数传递的参数])

间歇时间 毫秒
	1s = 1000ms

延迟执行定时器

延迟一段时间执行一个函数，仅且仅执行一次

setTimeout(要执行的函数,延迟时间，[给函数传递的参数])

什么时候使用定时器

当需要隔一段时间重复执行一段代码时用

setInterval()

当需要延迟一段时间执行一段代码时用

setTimeout()

清除定时器

关闭/停止定时器

```
var a = 0;
var s1 = setInterval(function() {//每隔1秒执行
    a++;
    console.log(a)
    if (a == 5) {
        clearInterval(s1); //注意不要直接关闭编号，每个浏览器的编号都不一样
    }
}, 1000)

var s2 = setTimeout(function() {//延迟6秒执行
    console.log(12312)
}, 6000)
```

