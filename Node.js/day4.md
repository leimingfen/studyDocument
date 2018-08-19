# Node.js - Day4

## 什么是Express.js
1. Express 是一个基于 Node.js 平台的极简、灵活的 web 应用开发框架；
2. Express 不对 Node.js 已有的特性进行二次抽象，只是在Node.js之上扩展了构建 Web 应用所需的基本功能。

> 总结什么是Express.js：是一个基于Node.js的Web开发框架。Express框架并没有覆盖或删除原生的API，而是基于原生的API，做了进一步的封装，提供了更好用的一些API，方便快速进行Web开发！
> res.render、res.json、res.redirect、req.query
> Node.js是Javascript的服务器端运行环境！express只是基础Node，提供了开发Web应用的框架和API。

## 如何创建基本的HTTP服务（新旧方式对比）
```
var express = require('express');

// 创建一个 app 出来
var app = express();

// 捕获 get 类型的 / 请求
app.get('/', function (req, res) {
  // 支持原生的 end 方法
  res.end('OK');
});
// 捕获 get 类型的 /a 请求
app.get('/a', function (req, res) {
  // 通过 express 封装的 send 方法，返回内容，会自动添加响应头，更加方便便捷
  res.send('<h1>你好啊</h1>');
});

// 启动 app 监听程序
app.listen(3000, function () {
  console.log('App running at http://127.0.0.1:3000');
});
```

## http模块原生`end`方法和 express中`send`方法的对比

## 根据不同的路由`method`和`url`响应不同的文本消息

## 根据不同的路由`method`和`url`响应不同的html页面

## 分别从原生和express的`app.js`中抽离`router`路由模块

## use、get/post、express.Router()的配合使用

## 中间件的概念
在自来水的处理过程中，中间的每一个处理环节，可以叫做中间件！
中间件就是用来处理原材料的，那么，在自来水处理过程中，处理的原料是水；在express中，中间件处理的原料是 request 对象 和 response 对象；
![自来水处理过程](images/自来水处理过程.jpg)

**概念：**中间件（Middleware） **是一个函数**，它可以访问**请求对象**（request object (req)）, **响应对象**（response object (res)）, 和 web 应用中处于请求-响应循环流程中的中间件，一般被命名为 next 的变量。

经过中间件的处理之后，express就向 req 和 res ,对象身上，挂在了一些好用的方法和属性
req.query
res.send()
res.json()

+ 中间件的功能包括：
 - 执行任何代码。
 - 修改请求和响应对象。
 - 终结请求-响应循环。
 - 调用堆栈中的下一个中间件。

## body-parser 中间件的使用步骤
在 express 中，可以使用 body-parser 第三方中间件，去帮我们出去 post 提交过来的数据
1. 使用 npm 安装
2. 导入 这个第三方中间件 模块
3. 使用 app.use()注册刚才导入的中间件，到 app身上


## 在Express中使用路由
1. 定义路由的 `router` 文件：
```
    var express = require('express');
    // 使用 express 的 Router() 方法，得到一个路由实例
    var router = express.Router();

    // 通过 Method 和 请求路径，分发不同的请求到不同的处理函数中
    router.get('/', function (req, res) {
      res.send('<h1>首页</h1>');
    }).get('/movie', function (req, res) {
      res.send('<h1>电影</h1>');
    });

    module.exports = router;
```
2. 导入路由并注册使用
```
    var express = require('express');
    // 导入路由
    var router = require('./router');

    // 创建一个 app 出来
    var app = express();
    // 注册路由
    app.use(router);

    // 启动 app 监听程序
    app.listen(3000, function () {
      console.log('App running at http://127.0.0.1:3000');
    });
```

## 在express中使用模板引擎
+ [MDN - JSON.stringify()](https://developer.mozilla.org/zh-CN/docs/Web/JavaScript/Reference/Global_Objects/JSON/stringify)
+ [MDN - FileReader](https://developer.mozilla.org/zh-CN/docs/Web/API/FileReader)
+ [MDN - FormData](https://developer.mozilla.org/zh-CN/docs/Web/API/FormData)
+ [Express - 中文网](http://www.expressjs.com.cn/)
+ [Express - 英文官网](http://expressjs.com/)
+ [Node.js 教程](http://www.runoob.com/nodejs/nodejs-tutorial.html)
+ [菜鸟教程 - Express 4.x API 中文文档](https://www.runoob.com/w3cnote/express-4-x-api.html)
+ [Express.js 4.0 的路由（Router）功能用法教學](https://blog.gtwang.org/programming/learn-to-use-the-new-router-in-expressjs-4/)
+ [github - art-template](https://github.com/aui/art-template)
+ [github - express-art-template](https://github.com/aui/express-art-template)
+ [github - ejs](https://github.com/mde/ejs)