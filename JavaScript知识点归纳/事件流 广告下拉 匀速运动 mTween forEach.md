# 事件流
事件冒泡

当触发一个元素的事件，这个元素以上的祖先节点都会触发对应的事件

```
var div1 = $(".div1")[0];
var div2 = $(".div2")[0];
var div3 = $(".div3")[0];

document.onclick = function (){
	alert('document')	
};

div2.onclick = function (){
	alert("div2")		
};
div3.onclick = function (){
	alert("div3")		
};
```
# 广告下拉

```
<!DOCTYPE html>
<html lang="en">

<head>
    <meta charset="UTF-8">
    <title></title>
    <style type="text/css">
    * {
        padding: 0;
        margin: 0;
    }
    
    .banner {
        width: 100%;
        height: 500px;
        background-color: #841682;
        position: absolute;
        top: -500px;
    }
    </style>
</head>

<body>
    <div class="banner"></div>
    <script>
    var banner = document.querySelectorAll('.banner')[0];
    var s1 = setInterval(function() {//把定时器赋值给s1
        var t = banner.offsetTop + 1;//每次增加top的值
        if (t > 0) {//如果当高度大于零
            t = 0;//把高度重新设置为0
            clearInterval(s1);//关闭定时器
            setTimeout(function() {//延迟3秒执行
                var s2 = setInterval(function() {//开定时器
                    var t2 = banner.offsetTop - 1;//每4毫秒减1px的Top值
                    if (t2 < -500) {//如果top的值小于-500
                        t2 = -500;//不再继续减
                        clearInterval(s2);//关闭定时器
                    }
                    banner.style.top = t2 + 'px';//满足以上条件执行
                }, 4)
            }, 3000)
        }
        banner.style.top = t + 'px';//满足以上条件执行
    }, 4)
    </script>
</body>

</html>

```
# 时间版运动
时间版运动
	1. 总路程    500 
	2. 持续时间   5s

过了1s中应该在哪个位置？  所处的位置 = 500/5*1

过了2s中应该在哪个位置？  所处的位置 = 500/5*2

过了5s中应该在哪个位置？  所处的位置 = 500/5*5

运动的位置 = 总距离/持续时间 * 已过去时间;

总距离 = 目标位置 - 起始位置

```
<!DOCTYPE html>
<html lang="zh-cn">
<head>
<meta http-equiv="Content-Type" content="text/html; charset=utf-8" />
<title></title>
<style>
	div {
		width: 100px;
		height: 100px;
		background: red;
		position: absolute;
		left: 100px;
		top: 50px;
	}
</style>
<script>
	/*
		1. 应对复杂的动画应用场景
		2. 需要兼容低版本
	*/
</script>
</head>

<body>
<input type="button" id="btn" value="运动" />
<div id="box"></div>
<script>

	var target = 500;  // 目标位置

	var d = 1000; // 持续时间
	
	var b = box.offsetLeft; // 起始位置
	
	var count = target - b;  // 总距离
	
	// 开始运动时间

	btn.onclick = function (){
		var now = Date.now(); // 开始运动的时间

		var timer = setInterval(function (){
			var t = Date.now() - now// 过去了多少时间 = 最新时间-最开始时间

			// 已过去时间不能超过持续时间
			if( t >= d ){
				t = d;
				clearInterval(timer);
			}
			
			box.style.left = count/d * t + b + 'px';

			console.log(t);	
		},4)
	}	

</script>
</body>
</html>
```
# mTween

```
<!DOCTYPE html>
<html lang="zh-cn">
<head>
<meta http-equiv="Content-Type" content="text/html; charset=utf-8" />
<title></title>
<style>
	div {
		width: 100px;
		height: 100px;
		background: red;
		position: absolute;
		left: 1000px;
		top: 50px;
	}
	#box2 {
		top: 550px;
	}
</style>
<script>
	
</script>
</head>

<body>
<input type="button" id="btn" value="运动" />
<input type="button" id="pause" value="暂停" />
<div id="box"></div>
<div id="box2"></div>
<script src="./tween.js"></script>
<script>
// left=100 => top=500 => width=1000 => height=0;
//回调函数 callback

	/*function fn(f){
		f(); // f就是回调函数
	}

	fn(function (){
		alert(1)	
	})*/

	btn.onclick = function (){

		mTween(box,"left",0,1000,"linear",function (){
			alert(1)
			mTween(box2,"top",200,1000,"backOut",function (){
					mTween(box,"width",300,1000,"linear")
			})
		})

	};

	pause.onclick = function (){
		clearInterval(box.timer);		
	};

	/*
		参数：
			element 要运动的元素    *
			attr 运动的属性			*
			target 目标位置			*
			duration 持续时间 ms    *

			fx 运动形式   默认值为"linear"  []
			callBack  调函数



	*/
	//var timer = null; // 不能使用同一个变量来存定时器的编号

	function mTween(element,attr,target,d,fx,callback){
				  //元素  属性  目标  几秒  匀速  回调
		var b = parseFloat(getComputedStyle(element)[attr]);  // 起始位置
		var c = target - b; //总距离
		var now = Date.now();  // 开始运动的时间

		fx = fx || 'linear'; //运动形式

		clearInterval(element.timer);
		element.timer = setInterval(function (){
			var t = Date.now() - now; //已过去时间

			if( t > d ){
				t = d;
				clearInterval(element.timer);
				typeof callback === 'function' && callback();
			}

			element.style[attr] = Tween[fx](t, b, c, d) + 'px';
			
		},4)

	}

	//mTween(box,"left",0,1000);

</script>
</body>
</html>
```
# forEach
```
arr2.forEach(function(item,index){
                    //值   值的下标
	console.log(item,index);
})
```