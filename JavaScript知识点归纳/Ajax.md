# Ajax
### Ajax是异步的JavaScript与XMl

### 作用：

### 与服务器进行数据交换 实现页面的局部更新

### 同步：

->指的是等其他请求执行完才能进行下一步

### 异步：

->指的是不需要等，全部请求同时进行

---

## get和post的区别

## get

http://www.123456.com/get.php?user=123&password=098778

get发送数据的方式在?后面查询信息

浏览器对url地址有长度的限制，所以说get数据数量会有限制，而且不安全，数据可以直接在url上看到

## post

http://www.123456.com/get.php

发送数据的方式

在HTTP请求主题发送的

大小限制：理论上没有，但服务器会有限制

理论上是安全的，但不排除有恶意攻击

设置请求头：

xhr.setRequestHeader( 'Content-Type','application/x-www-form-urlencoded');

---

例子：www.baidu.com

### 请求 request

post 119.75.213.61:443 1.1.1 请求行

cookie:请求的信息

Connection:Keep-Alive

Content-Encoding:gzip

body  请求数据的主体

---
### 相应 response
1.1.1 200 ok 200代表成功

cookie: 相应信息，消息

Connection:Keep-Alive

Content-Encoding:gzip

body 主体

二进制文本


---
### POST方式发送


http状态码

https://baike.baidu.com/item/HTTP%E7%8A%B6%E6%80%81%E7%A0%81/5053660?fr=aladdin

200 ok 

304 Not Modified

404 Not found

502 Bad Gateway


---

### ajax工作流程
初始化，未发送			0	UNSENT

准备数据，连接地址		1	OPENED

返回响应头				2	HEADERS_RECEIVED   未返回内容，只返回了响应头

接收数据中				3	LOADING            返回内容，数据量大，分批返回

接收数据完毕			4	DONE               数据完全接受完成

#  ajax上传
```
<!DOCTYPE html>
<html lang="zh-cn">
	<head>
		<meta http-equiv="Content-Type" content="text/html; charset=utf-8" />
        <title></title>
		<style>
			*{
				padding: 0;
				margin: 0;
			}
			#box {
				width: 500px;
				height: 30px;
				border: 1px solid #000;
				position: relative;
			}
			#box p {
				width: 100%;
				text-align: center;
				line-height: 30px;
				position: relative;
				z-index: 10;
			}
			#bar {
				width: 0px;
				height: 100%;
				background: red;
				position: absolute;
				left: 0;
				top: 0;
			}
		</style>
		<script>
			/*
				js不能读取文件，只有服务器的语言才能读取
			*/
			//js.delectFile("c")
		</script>
	</head>

	<body>
		<input type="file" id="inputFile" name="file">
		<input type="button" id="btn" value="上传" />
		<div id="box">
			<p id="text">0%</p>
			<div id="bar"></div>
		</div>
		<script>
			btn.onclick  =function (){
				// 上传
				let xhr = new XMLHttpRequest();

				xhr.open(
					'post',
					'http://localhost:8088/backend/post_file.php',
					true
				);

				// 监控上传进度
				xhr.upload.onprogress = function (ev){
					console.log(ev.loaded); // 上传大小	
					console.log(ev.total); //  总大小	
					console.log(Math.round(ev.loaded/ev.total*100)+'%');

					let scale = ev.loaded/ev.total;

					text.innerHTML = Math.round(ev.loaded/ev.total*100)+'%';
					bar.style.width = scale * 500 + 'px';

				}


				xhr.onload = function (){
					console.log(xhr.responseText);	
				};

				// 找到要上传的文件，把文件转成二进制的

				console.log(inputFile.value);  // 图片所在的地址
				// 真正上传的资源，放在元素的files属性中
				console.dir(inputFile.files[0]);

				// 高版本浏览器 FormData

				let f = new FormData();
				f.append('file',inputFile.files[0]);

				xhr.send(f);

			};
		</script>
		
	</body>
</html>
```



