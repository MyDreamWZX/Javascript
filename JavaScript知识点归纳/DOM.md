## API接口

## API（Application Programming Interface,应用程序编程接口）是一些预先定义的函数

## 调用这些函数，实现自己的目的，无需知道实现原理


## DOM:Document Object Model
## 	处理可扩展标志语言（XML、HTML）的标准编程接口(API)
## 		赋予了操作页面的能力

## DOM是针对XML的扩展，应用于HTML的应用程序编程接口API，制定这些接口的目的是为了能以编程的方法操作这个 HTML 的内容

## DOM把整个应用程序界面映射为一个多层的节点结构，可以看做是一个文档树（或节点树），组成这个树的每一部分称之为节点，每一个节点都是一个对象。

## 通过DOM提供的接口，允许开发人员可以很方便的删除、添加、替换、修改任何节点。

## 元素节点  每个 HTML元素
## 属性节点  HTML元素的属性
## 文本节点  HTML元素内的文本
## 注释节点  注释 <!---->
## 文档节点  整个文档document


## 通过一个对象调用这些接口 document

```
元素节点  每个 HTML元素       	nodeType    1    nodeName   标签名（全大写）
属性节点  HTML元素的属性		nodeType    2    nodeName   属性名
文本节点  HTML元素内的文本	nodeType    3    nodeName   #text
注释节点  注释 <!---->		nodeType    8    nodeName   #comment
文档节点  整个文档document	nodeType    9    nodeName   #document



NodeType	Named Constant
1				ELEMENT_NODE
2				ATTRIBUTE_NODE
3				TEXT_NODE
4				CDATA_SECTION_NODE
5				ENTITY_REFERENCE_NODE
6				ENTITY_NODE
7				PROCESSING_INSTRUCTION_NODE
8				COMMENT_NODE
9				DOCUMENT_NODE
10				DOCUMENT_TYPE_NODE
11				DOCUMENT_FRAGMENT_NODE
12				NOTATION_NODE


通过一个对象调用这些接口 document
```
# 节点之间的关系
## 包含是父子关系，并列是兄弟关系

## 祖先节点：当前节点往上的所有节点

## 子孙节点：当前节点往下的所有节点

## node.parentNode 			--- 获取父节点

## node.children 			--- 获取所有子元素节点

## node.childNodes			--- 获取所有子节点

## node.previousElementSibling	--- 获取上一个兄弟节点

## node.nextElementSibling 		--- 获取下一个兄弟节点

## node.firstElementChild 		--- 获取元素中第一个子节点

## node.lastElementChild 		--- 获取元素中最后一个子节点

# 上下两个div添加颜色
```
<!DOCTYPE html>
<html lang="zh-cn">
<head>
<meta http-equiv="Content-Type" content="text/html; charset=utf-8" />
<title></title>
<style>
	div{
		width: 500px;
		height: 30px;
		background: red;
		margin: 10px;
	}
</style>
<script>
	
</script>
</head>

<body>

<div></div>
<div></div>
<div></div>
<div></div>
<div></div>
<div></div>
<div></div>
<div></div>
<div></div>
<div></div>
<div></div>
<div></div>
<div></div>
<div></div>

<script>
	function pSibling(element){
		return element.previousElementSibling;
	}
	var divs = document.getElementsByTagName('div');

	Array.from(divs).forEach(function (item){
		item.onmouseover = function (){
			this.style.background = 'blue';	
			// 上一个兄弟
			if(this.previousElementSibling){
				this.previousElementSibling.style.background = 'green';
			}
			if(this.nextElementSibling){
				this.nextElementSibling.style.background = 'green';
			}
			
			
		};
		item.onmouseout = function (){
			this.style.background = '';	
			if(this.previousElementSibling){
				this.previousElementSibling.style.background = '';
			}
			if(this.nextElementSibling){
				this.nextElementSibling.style.background = '';
			}
		};
	})

</script>
</body>
</html>
```
# 小总结
## DOM

## 文档树

## 节点 => 对象

## 1. 获取节点

## getElementById()

## getElementsByTagName()

## getElementsByClassName()

## querySelector

## querySelectorAll
```
节点分类：       nodeType       nodeName
元素节点     	    1	       大写标签名
属性节点     	    2	       属性名
文本节点     	    3	       #text
注释节点     	    8	       #comment
文档节点     	    9	       #document
```
## 节点关系

## 父子关系 兄弟关系

## 祖先关系 子孙关系

## 上一个兄弟    previousElementSibling

## 下一个兄弟    nextElementSibling

## 子元素        childNodes  children

## 父元素		  parentNode

## 第一个子元素  firstElementChild

## 最后一个子元素 lastElementChild

# 设置/删除/添加 属性
对DOM节点操作
	获取
	创建
	删除
	修改
	替换

innerHTML 赋给innerHTML的值是一个字符串结构

1. 创建一个元素

	documnet.createElement("标签名")
2. 向一个元素追加一个子节点

	element.appendChild(元素);
	
	返回值是追加的元素
3. 往一个节点的指定子节点前边插入一个节点

element.insertBefore(newElement,childNode2)

newElement 要插入的元素

childNode2 被插入的目标元素

参数：
newElement必须要存在，并且是一个节点（node）

childNode2可以不存在，insertBefore功能就类似于appendChild

把newElement插入到childNode2前边

4. 替换指定的子节点
 
element.replaceChild(node,childNode)

node用来替换的节点，childNode被替换的子节点

两个参数都必须写。

5. 删除指定的子节点

element.removeChild(childNodes)

childNode.remove()   把自己从父节点删除

# 小练习 新建文件夹
```

<!DOCTYPE html>
<html lang="en">

<head>
    <meta charset="UTF-8">
    <title></title>
    <style type="text/css">
    .box {
        width: 700px;
        height: 500px;
        background-image: url(./image/bg.png);
        background-repeat: no-repeat;
        background-size: 100% 100%;
        margin: 0 auto;
    }

    .main {
        width: 690px;
        height: 136px;
        margin: 0 auto;
        position: relative;
        top: 180px;
        text-align: center;
    }

    .bottom {
        width: 132px;
        height: 106px;
        margin: 0 auto;
        position: relative;
        top: 195px;
    }

    .bottom img {
        cursor: pointer;
    }

    .main>div {
        width: 130px;
        height: 130px;
        display: inline-block;
        position: relative;
        box-sizing: border-box;
    }

    .main div img {
        position: relative;
        top: 28px;
        display: block;
        margin: 0 auto;
    }

    .main div span {
        position: relative;
        top: 27px;
        font-size: 13px;
    }

    input {
        position: absolute;
        left: 0;
    }

    .div-active {
        border: 2px solid #b4a3c2;
        border-radius: 10px;
        background-color: rgba(76, 71, 71, 0.26);
    }

    .main div input {
        display: none;
    }
    </style>
</head>

<body>
    <div class="box">
        <div class="main" id="main">
            <!-- <div class="div-active">
                <input type="checkbox">
                <img src="image/case.png" />
                <span>新建文件夹</span>
            </div> -->
        </div>
        <div class="bottom">
            <img src="./image/new-case.png" id="newCase" />
            <img src="./image/detel.png" id="detel" />
        </div>
    </div>
    <script>
    // var data = [{
    //     img: 'image/case.png',
    //     span: '新建文件夹'
    // }];
    var data = ['image/case.png', '新建文件夹'];

    var main = document.getElementById('main');

    // var mainDiv = document.querySelectorAll('.main>div');
    var mainDiv = main.getElementsByTagName('div');

    var newCase = document.getElementById('newCase');
    var detel = document.getElementById('detel');
    var n = 0;

    newCase.onclick = function() {
        n++;
        if (n < 5) {
            var divs = document.createElement('div'); //创建元素
            var input = document.createElement('input'); //创建元素
            var img = document.createElement('img'); //创建元素
            var span = document.createElement('span'); //创建元素
            divs.appendChild(input) //添加元素
            divs.appendChild(img) //添加元素
            divs.appendChild(span) //添加元素
            divs.querySelector('input').setAttribute('type', 'checkbox') //修改元素属性
            divs.querySelector('img').setAttribute('src', data[0]) //修改元素属性
            divs.querySelector('span').innerHTML = data[1] //修改元素属性
            main.appendChild(divs)

 

            for (var i = 0; i < mainDiv.length; i++) { 
                mainDiv[i].index = i;
                mainDiv[i].onmouseover = function() {//鼠标经过添加class
                    var thisInput = this.querySelector('input');
                    this.className = 'div-active';
                    thisInput.style.display = 'block';
                }
                mainDiv[i].onmouseout = function() {//鼠标离开判断点没点，如果点了保持class，没点取消class
                    var thisInput = this.querySelector('input');
                    if (thisInput.checked == true) {

                    } else {
                        this.className = '';
                        thisInput.style.display = '';
                    }

                }

            }
        }

    }
    var checked = document.getElementsByTagName('input');
    detel.onclick = function() {//点击删除按钮

        for (var i = 0; i < checked.length; i++) {
            checked[i].index=i;
            if (checked[i].checked==true) {//单机了单选框的对应下标的div删除
                main.removeChild(mainDiv[i]);
                i--;
            }
        }
        n=checked.length;
    }
    </script>
</body>

</html>
```
# 消除表情小游戏
```
<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<title>Game_main</title>
<link rel="stylesheet" href="style/Game_main.css">
<style>
.content {
	-overflow: hidden;
}
</style>
</head>
<body>
<div id="wrap">
<div class="head">
	<div id="log"></div>
	<h3 class="title">你的鼠标有多快?</h3>
	<p class="explain">游戏说明：“点击游戏”，随机掉下表情点中它，千万别让它掉下去！！</p>
</div>
<div class="content">
	<div class="win">
		<span class="winNum">0分</span>
		<p>得分</p>
	</div>
	<div class="lose">
		<span class="loseNum">0分</span>
		<p>失分</p>
	</div>
	<a href="javascript:;" class="btn">开始游戏</a>
	<img src='img/1.png' id="runImg" style="position: absolute;left:0;top:-54px;">
</div>

</div>
<script src="../utils.js"></script>
<script>
var arr = [
	'./img/1.png',
	'./img/3.png',
	'./img/4.png',
	'./img/5.png',
	'./img/6.png'
]

var btn = $(".btn")[0];
var win = $(".win")[0];
var lose = $(".lose")[0];
btn.onclick = function (){
	mTween(win,{left:-100},500)	
	mTween(lose,{left:-100},500)	
	mTween(this,{bottom:0,opacity:0},500,'linear',actionImg)	
};

// 调整 src随机得到地址 得到随机的left
var runImg = $("#runImg");
var content = $(".content")[0]; // 大框框
var time = 5000;
var winNum = 0;
var loseNum = 0;

var winNumSpan = $(".winNum")[0];
var loseNumSpan = $(".loseNum")[0];

function actionImg(){
	runImg.style.top = '-54px';
	// 控制随机去src地址的
	var index = Math.round(Math.random()*(arr.length-1))

	runImg.onload = function (){
		// 等图片加载完成之后，获取offsetHeight是正确的值
		var target = content.clientHeight - runImg.offsetHeight;
		time -= 100;
		mTween(runImg,{top:target},time,'linear',function (){
			// 执行了这个回调函数，说明没点到
			runImg.style.top = '-60px';
			shake(content,"top",50,function (){
				loseNum++;  // 失分
				loseNumSpan.innerHTML = loseNum + '分';
				if(loseNum === 3){
					// 异步，当操作的DOM频繁，当DOM执行完后，在执行这段代码，这时候使用setTimeout
					/*setTimeout(function (){
						alert("你失败了，重新开始吧");		
					});*/

					mTween(win,{left:14},500)	
					mTween(lose,{left:14},500)	
					mTween(btn,{bottom:20,opacity:1},500,'linear')
					btn.innerHTML = '重新开始';
					loseNum = 0;
					winNum = 0;
					time = 1000;
					winNumSpan.innerHTML = winNum + '分';
					loseNumSpan.innerHTML = loseNum + '分';
					return;
				}

				
				actionImg();	
			})	
		})	
	};
	runImg.src = arr[index];  // 有一个加载的过程

	// 随机left位置
	var left = Math.round(Math.random()*(content.clientWidth - runImg.offsetWidth));

		runImg.style.left = left + 'px';
}


// 点中了

runImg.onclick = function (){
	console.log('点中了');
	// 先让img停下来
	clearInterval(runImg.timer);
	shake(runImg,"left",30,function (){
		winNum++; // 得分
		winNumSpan.innerHTML = winNum + '分';


		actionImg();

	})
};





</script>
</body>
</html>
<!-- <script src="js/Game_main.js"></script> -->
<!-- 
1. 点击开始游戏  动画
2. 让这个img随机的到一个src地址，并且left随机计算（0-框框width-img的width）
3. 让img运动 目标是框框height-img的height
4. 运动过程中点中了：
	img抖动 抖完之后
		top为0 left随机算出，src随机得到一个地址
		让img运动 目标是框框height-img的height
	img抖动 抖完之后
		top为0 left随机算出，src随机得到一个地址
		让img运动 目标是框框height-img的height

5. 运动过程中没有点中了：
	框框抖动，抖动之后
		img的top为0 left随机算出，src随机得到一个地址
		让img运动 目标是框框height-img的height
	框框抖动，抖动之后
		img的top为0 left随机算出，src随机得到一个地址
		让img运动 目标是框框height-img的height


-->
```
# 登陆框居中显示
居中的元素宽高不固定

元素的left值和top值

元素的left值 = (可视区的宽 - 元素所占的宽）/2

1. 可视区的宽/高

	document.documentElement 就是html元素
	
	document.documentElement.clientWidth
	
	document.documentElement.clientHeight
2. 元素所占的宽/高
	
    element.clientWidth/clientHeight  不包含border
	
    element.offsetWidth/offsetHeight  包含border

浏览器改变尺寸触发一个事件
	window.onresize = function(){}

出现滚动条，滚动条向下拉，依然让box出在中心，需要加上页面被卷去的高度

浏览器滚动条滚动的时候触发的事件
	window.onscroll = function(){}

页面滚动的距离
	y轴的：
	
	document.document.scrollTop  ie和ff放在html
	
	document.body.scrollTop      chrome放在body
	x轴的：
	
	document.document.scrollLeft
	
	document.body.scrollLeft
```
var box = document.getElementById("box");

box.style.left = (document.documentElement.clientWidth - box.offsetWidth)/2  + 'px';
box.style.top = (document.documentElement.clientHeight - box.offsetHeight)/2  + 'px';

window.onresize = function (){
	//document.title = "调整了大小";

	/*document.title = document.documentElement.clientWidth + '|' + document.documentElement.clientHeight;*/
	box.style.left = (document.documentElement.clientWidth - box.offsetWidth)/2  + 'px';
	box.style.top = (document.documentElement.clientHeight - box.offsetHeight)/2  + 'px';	
};

window.onscroll = function (){
	//console.log("滚动了");
	// 页面被卷曲的高度
	//console.log(document.documentElement.scrollTop); 
	//console.log(document.body.scrollTop);

	var scrollTop = document.documentElement.scrollTop || document.body.scrollTop;

	var scrollLeft = document.documentElement.scrollLeft || document.body.scrollLeft;

	console.log(scrollTop,scrollLeft); 
	box.style.top = (document.documentElement.clientHeight - box.offsetHeight)/2 + scrollTop + 'px';
};
```
# 定位父级
```
<!DOCTYPE html>
<html lang="zh-cn">
<head>
<meta http-equiv="Content-Type" content="text/html; charset=utf-8" />
<title></title>
<style>
	body {
		margin: 0;
	}
	div {
		width: 500px;
		height: 500px;
		background: red;
		font-size: 20px;
		color: #fff;
	}
	.div1 {
		position: absolute;
		left: 100px;
	}
	.div2 {
		width: 300px;
		height: 300px;
		background: green;
		position: absolute;
		left: 30px;
		top: 0;
	}
	.div3 {
		width: 200px;
		height: 200px;
		background: blue;
	}
</style>
<script>
	
</script>
</head>

<body>
<div class="div1">
	div1
	<div class="div2">
		div2
		<div class="div3">
			div3	
		</div>
	</div>
</div>
<script>
	/*
		定位父级
			element.offsetParent

			可获取到最近的定位父级，如果没有定位元素，定位父级默认为body

		偏移量
			offsetLeft 相对于定位父级左边的偏移量	
			offsetTop 相对于定位父级上边的偏移量

		最好是把父级和自己都加上定位

	*/

	var div2 = document.querySelector(".div2");
	var div1 = document.querySelector(".div1");
	var div3 = document.querySelector(".div3");

	console.log( div2.getBoundingClientRect() );

</script>
</body>
</html>
```