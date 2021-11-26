---
title: express笔记
categories: 技术
tags: express
date: 2021-11-26
---
## express笔记

#### 一、express安装

1.npm初始化

`npm init`

2.npm安装

`npm install`

3.express安装

`npm install express --save`

4.express脚手架express-generator安装

`npm install express-generator`

`npm install -g express-generator(全局安装，使用express -v查看版本)`

5.使用pug模板引擎创建名为myapp的express应用

`express --view=pug myapp`

`set DEBUG=myapp:* & npm start`



#### 二、Express路由

1.路由简介

**路由**表示应用程序端点 (URI) 的定义以及响应客户端请求的方式。它包含一个请求方时（methods）、路径（path）和路由匹配时的函数（callback）

2.路由方法

get、post、put、head、delete、options、trace、copy、lock、mkcol、move、purge、propfind、proppatch、unlock、report、mkactivity、checkout、merge、m-search、notify、subscribe、unsubscribe、patch、search 和 connect

3.路径

Express路径包含三种表达形式，分别为字符串、字符串模式、正则表达式

1. 字符串路径

   `app.get("/login",function(req,res){ res.send("哈哈哈哈，嘻嘻嘻嘻"); })`

2. 字符串模式路径

   `app.get("/ab+cd",function(req,res){ res.send("哈哈哈哈，嘻嘻嘻嘻"); })`

3. 正则表达式路径

   `app.get(/^a/,function(req,res){ res.send("哈哈哈哈，嘻嘻嘻嘻"); })`

4.基础路由

`const express = require("express");`
`var app = express();`

`app.get("/",function(req,res){`
	`res.send(<h1>主页</h1>)`
`});`
`app.get("/login",function(req,res){`
	`res.send(<h1>登录</h1>)`
`});`
`app.get("/register",function(req,res){`
	`res.send(<h1>注册</h1>)`
`});`

`app.listen(8080)`

5.动态路由

`const express = require("express")`
`var app = express()`

`app.get("/",function(req,res){`
	`res.send(<h1>oh no</h1>)`
`});`
`app.get("/login/:id",function(req,res){`
	`res.send(req.params)`
`});`

`app.listen(8080)`

#### 三、get请求

GET 请求可被缓存
GET 请求保留在浏览器历史记录中
GET 请求可被收藏为书签
GET 请求不应在处理敏感数据时使用
GET 请求有长度限制
GET 请求只应当用于取回数据

1.获取get请求

http://localhost:8080/login?goods=0001&detail=0001

通过req.query或者req.query.goods与req.query.detail获取

`const express = require("express")`
`var app = express();`

`app.get("/",function(req,res){`
	`res.send("主页");`
`});`

`app.get("/login",function(req,res){`
	`console.log(req.query);`
	`res.send("接收到登录提交的用户与密码，user："+req.query.user+"， password："+req.query.password);`
`});`

`app.listen(8080)`

2.获取post请求

form表单进行post请求，enctype属性一般设置为“application/x-www-form-urlencoded”，如果设置成multipart/form-data，则多用于文件上传

`<form action="#" method="post" enctype="application/x-www-form-urlencoded"></form>`

使用npm提供的body-parser或者connect-multiparty来获取post数据

1. body-parser

   Express中默认都使用body-parser作为请求体解析post数据，这个模块也能解析：JSON、Raw、文本、URL-encoded格式的请求体。

   安裝：

   `npm install body-parser --save`

   引用：

   `const bodyParser=require("body-parser")`

   `// 解析以 application/json 和 application/x-www-form-urlencoded 提交的数据`
   `var jsonParser = bodyParser.json()`
   `var urlencodedParser = bodyParser.urlencoded({ extended: false })`

   bodyParser.json()很明显是将json作为消息主题，再且常见的语言和浏览器大都支持json规范，使得json处理起来不会遇上兼容性问题。
   application/x-www-form-urlencoded：
   如果form表单不设置enctype属性，那么他默认就会是这种。
   之后获取数据

   `app.post("/",urlencodedParser,function(req,res){ res.send(req.body); })`

   在中间添加urlencodedParser，请求是依然使用req.body获取数据

2. connect-multiparty

   connect-multiparty多用于文件上传，但也可以访问到post请求的数据

   安装：

   `npm install connect-multiparty --save`

   引用：

   `const express=require("express")`
   `const multipart = require('connect-multiparty');`
   `var multipartMiddleware = multipart()`

   `var app=express()`

   `app.post('/',multipartMiddleware,function(req,res){`
   	`res.send(req.body)`
   `});`

   `app.listen(8080)`

   推荐使用body-parser