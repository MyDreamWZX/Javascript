# 表单
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
		<!--
			form作用：提交数据
				
			method: 提交方式 get post

			http://www.123.com/?userName=wangyun&password=123
			表单控件上name是和后端进行约定的，代表特殊意义
		-->
		<form method="get" action="./1.php">
			用户名<input type="text" name="userName">
			密码<input type="password" name="password" >
			<select name="select">
				<option value="100011">北京</option>
				<option selected value="100012">上海</option>
			</select>
			<input id="btn" type="submit" value="提交" />
		</form>
		<form method="get" action="./1.php" >
			用户名<input type="text" name="userName">
			密码<input type="password" name="password" >
			<input type="button" value="提交" />
			<input type="button"  id="resets" value="重置" />
		</form>
		<a id="linkA" href="http://www.123.com">miaov</a>
		<script>
			/*
				浏览器的默认行为
					不用写任何js代码，浏览器就有的一些行为
						a标签跳转链接
						选中文字

				默认行为触发和开发者监控对应的事件
					监控对应的事件先触发,可以在触发默认行为之前取消默认行为
			*/

			linkA.onclick = function (){
				console.log(123);

				return false;	
			};

			document.forms[0].onsubmit = function (){
				if(this.userName.value === ''){
					return false;
				}	
			};

			document.forms[0].onreset = function (){
				
			};


		</script>
	</body>
</html>
```
# BOM
BOM --- 浏览器对象模型

Browser Object Model，简称BOM

关于如何控制浏览器的一些东西

window

顶级/全局对象

全局声明的变量和函数都会放在window上

既是通过js访问浏览器窗口的接口
# window.open
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
				一打开页面，就打开新窗口
					ff和chrome因为安全限制，做一个限制
					ie直接打开新窗口

				点击页面，打开新窗口
					直接打开新窗口
			*/

			//window.open();

			// 在ie下必须等页面加载完了在给document绑定事件
			

		</script>
	</head>

	<body>
		<script>
			/*
				打开一个新窗口
					参数：
						1.指定要打开的页面地址。
						2.打开方式 ： _blank _self ... iframName
						3.浏览器的窗口特征 （宽，高，窗口位置等）
							设置width、height、left、top
			*/
			window.onload = function(){
				document.onclick = function (){
					window.open('http://www.miaov.com',"_blank","width=500,height=500,left=400,top=100");
				}
			};
		</script>
	</body>
</html>
```
# window.close
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
				一打开页面，就关闭窗口
					ff和chrome直接关闭
					ie下 询问是否关闭

				点击页面，关闭窗口

					chrome直接关闭
					ff不关闭
						只能关闭通过window.open打开的页面
					ie下 询问是否关闭

			*/
			
			//window.close();
			window.onload = function(){
				document.onclick = function (){
					window.open('./test-close.html')
				};
			};		
		</script>
	</head>

	<body>
		<script>
			
		</script>
	</body>
</html>
```
# 用户代理信息
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
				window.navigator.userAgent
					chrome
						Mozilla/5.0 (Windows NT 6.3; WOW64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/56.0.2924.87 Safari/537.36
					ff
						Mozilla/5.0 (Windows NT 6.3; WOW64; rv:54.0) Gecko/20100101 Firefox/54.0
					ie
						11
							Mozilla/5.0 (Windows NT 6.3; WOW64; Trident/7.0; .NET4.0E; .NET4.0C; .NET CLR 3.5.30729; .NET CLR 2.0.50727; .NET CLR 3.0.30729; MANMJS; rv:11.0) like Gecko
						8
							Mozilla/4.0 (compatible; MSIE 8.0; Windows NT 6.3; WOW64; Trident/7.0; .NET4.0E; .NET4.0C; .NET CLR 3.5.30729; .NET CLR 2.0.50727; .NET CLR 3.0.30729; MANMJS)
				内核
					https://jingyan.baidu.com/article/5553fa82d50eaf65a339346c.html
			*/
			console.log(window.navigator.userAgent);
			var userAgent = window.navigator.userAgent;

			if( userAgent.indexOf("MSIE 7.0") !== -1 ){
				alert("ie7")
			}

			// iPhone Androied  iPad

			

			function isMobile(){
				var arr = ['iPhone','Android','iPad'];
				var userAgent = window.navigator.userAgent;

				for( var i = 0; i < arr.length; i++ ){
					if(userAgent.indexOf(arr[i]) !== -1){
						return true;
					}
				}

				return false

			}

			console.log(isMobile());

		</script>
	</head>

	<body>
		
	</body>
</html>
```
# url组成
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
				http://123.com/
				https
				file

				http://www.123.com:80/home/index.html?miaov=ketang&video=study#vip=123&videoId=456

				https://www.baidu.com/s?wd=miaov
				
				https/http:// 			===>	protocol 	传输协议
				123.com 			===>	host name 	主机名
				80  				===>	port		端口   
				home/index.html 		===>	path 		路径
				?123=ketang&video=study ===>	search 		查询数据
				#vip=123&videoId=456 	===>    hash 		锚点

			*/
		</script>
	</head>

	<body>
		<a href="#test">定位</a>
		<div style="margin-top: 3000px;height: 1000px;" id="test">定位到这里</div>
	</body>
</html>
```
