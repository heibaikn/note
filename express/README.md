# express

通过学习开源项目来整理笔记，[地址请戳这里](https://github.com/heibaikn/node-elm.git)

##  api
主要有 express(),Request,Response,Router四个对象
### api-express()
```js
var express = require('express');
var app = express();

app.set()  //设置全局变量
app.use(); //挂载中间件
app.listen(); //绑定和监听端口
app.all();  //Request Method方法 all()截取所有请求
app.get();app.post();app.all();app.put();app.delete();
```
### api-Request
```js
app.use(express.json()) // for parsing application/json
app.use(express.urlencoded({ extended: true })) // for parsing application/x-www-form-urlencoded
router.post('/book',function(request,response){
  request.route  //路由信息
  request.query.t //获取query参数 当?t=1 =>1
  request.params.id //获取params值 当/book/:id && /book/1 =>1
  request.body //xhr 提交参数
})
```
### api-Response
```js
router.post('/',function(request,response){
  response.render('index') //渲染模板 返回html
  res.status(200).json({ msg: 'ok' }) //返回json格式
  res.send({ some: 'json' })//  智能化返回 可 json array html Buffer
})
```
### api-Router
```js
router.all() //Request Method方法 all()截取所有请求
router.get()
```
