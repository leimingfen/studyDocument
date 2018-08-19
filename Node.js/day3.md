# Node.js - day3

## 复习
+ 掌握同步、异步、异步嵌套的区别
 - 同步：严格按照代码书写顺序执行，代码效率不高，为什么？因为所有代码都是由主线程执行的
 - 异步：效率高，为什么？因为耗时的操作都由子线程执行？抢先机制，无法保证执行顺序；
 - 异步嵌套：效率也比较高，同时能够保证执行的顺序！
+ 掌握同步和异步方法如何捕获错误
 - 同步：只能使用try catch,如果不是用try catch 出错之后，程序会崩溃；
 - 异步：只能使用回调函数中提供的第一个参数Error对象来判断；不能使用try catch;同步代码出错之后不会阻止后续代码执行！
+ 了解Node中模块化以及如何实现模块化
 - 主要解决了什么问题：主要解决了JS文件之间的依赖关系；
 - 通过 module， require， exports
+ 掌握用户模块向外暴露成员的两种方式
 - 向global这个全局对象挂载成员【不推荐】
 - 推荐使用module.exports或者exports来向外暴露成员
+ 掌握module.exports和exports之间的关系
 - 模块最终向外暴露的成员，以module.exports指向的对象为准
+ 了解用户模块和第三方模块的查找规则
 - index -> index.js -> index.json -> index.node
+ 掌握art-template结合Node的使用方式
 - template.compile得到render函数，再调用render('要渲染的数据')
 - template.render('要渲染的模板字符串', 要渲染的数据对象)
 - template('要渲染的模板文件的路径', 要渲染的数据对象)
+ 了解服务端渲染和客户端渲染的各自特点
+ 掌握fs模块的readdir和stat方法的使用
+ 掌握count计数器的使用原理

## `path`路径处理模块
+ 拼接路径  path.join
+ 获取文件名 path.basename(path[, ext])
+ 获取扩展名 path.extname(path)
+ 获取文件所在路径 path.dirname(path)



## 构建基本的英雄页面并处理静态资源


## 渲染英雄列表


## 展示添加英雄页面


## 封装render函数


## 将代码进行模块化处理
+ 抽离`render`模块
+ 抽离`router`模块
+ 抽离`handler`模块
+ 抽离`model`模块


## Ajax异步post提交英雄表单数据


## 使用`querystring`模块解析表单Post提交的数据


## 处理查看info页面
### 使用`url`核心模块解析处理客户端请求的URL地址


## 英雄信息的编辑功能


## 302重定向
```
res.writeHeader(302, { 'Location': '/' });
res.end();
```

## 封装`res.json`方法和`res.redirect`方法

## 删除英雄信息
### 使用同步方式删除
### 使用异步方式删除、结合模板引擎


## 相关文章
+ [felixge/node-formidable](https://github.com/felixge/node-formidable)
+ [Node中使用 302 重定向](https://stackoverflow.com/questions/4062260/nodejs-redirect-url)
+ [Nodejs基础：路径处理模块path总结](http://www.cnblogs.com/chyingp/p/node-learning-guide-path.html)
+ [FormData 对象的使用](https://developer.mozilla.org/zh-CN/docs/Web/API/FormData/Using_FormData_Objects)
+ [深入浅出ES6（六）：解构 Destructuring](http://www.infoq.com/cn/articles/es6-in-depth-destructuring/)
+ [MDN - Array.prototype.some()](https://developer.mozilla.org/zh-CN/docs/Web/JavaScript/Reference/Global_Objects/Array/some)
+ [URL中的hash（井号）](http://www.cnblogs.com/joyho/articles/4430148.html)
+ [借助node实战JSONP跨域](http://www.cnblogs.com/giggle/p/5496596.html)
+ [jQuery ajax - ajax() 方法](http://www.w3school.com.cn/jquery/ajax_ajax.asp)