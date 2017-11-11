# JSONP

从后端响应的数据，流行的数据格式是json数据格式，是一个字符串，是json字符串。

官网：http://json.org/

JSON(JavaScript Object Notation) 是一种轻量级的数据交换格式

JSON格式的结构：

1. “名称/值”对的集合  '{"key":0,"key2":"string"}'
2. 
	key值必须写双引号、值是任意类型，不能是函数

2. 值的有序列表    '[]'
3. 
	值不能是函数

JSON字符串 -> 可用的对象

---

标准浏览器下：全局对象JSON 

低版本浏览器：https://github.com/douglascrockford/JSON-js  引入json2.js

JSON.parse(JSON字符串)

下载和上传

---

上传的时候，会把读到的文件转成二进制的，from表单设置一个enctype="multipart/form-data"

上传：

1. 使用form表单做上传

修改上传大小

---

wamp\bin\apache\Apache2.2.21\bin\php.ini

upload_max_filesize 			上传大小

post_max_size 					post发送的数据

# 解决跨域

所谓同源是指，域名，协议，端口相同。

域名  是ip的别名（小名）

baidu.com  taoba.com  gome.com.cn  一级域名

news.baidu.com/              二级域名

git.oschina.net/

abc.news.baidu.com/          三级域名

协议 服务器（客户端）进行通信的一种约定

https

http

ftp

file

端口 
https  443

http 80

ftp  22

file 

http://asd.com:80

http://asd.com:8080

这三个有一个不同，就产生跨域

解决跨域

-----------------------

1. 设置允许跨域的头部

在请求的这个域上设置一个header

比如http://localhost:3000/访问http://localhost:8888/test  会产生跨域

在http://localhost:8888/这个域下设置header，允许3000来访问

res.header("Access-Control-Allow-Origin", "http://localhost:3000");

res.header("Access-Control-Allow-Origin", "*");

2. 代理 

请求自己域下的后端，自己域下的后端请求目标域的接口

比如http://localhost:3000/访问http://localhost:8888/test  会产生跨域

比如http://localhost:3000/访问http://localhost:3000/abc.php

让http://localhost:3000/abc.php 去访问http://localhost:8888/test

3. jsonp = json + padding

1. 先创建一个script标签，src赋值地址

2. 访问的地址返回数据，数据中会有一个函数的执行

3. 在全局放一个函数，返回了数据，数据中或有函数执行，就会执行这个函数

4. 可以通过函数的参数拿到所需要的数据
