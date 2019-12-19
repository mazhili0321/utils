# 解决 node express 跨域问题

```javascript
const http = require('http')
const express = require('express')

const app = express()
//设置跨域访问
app.all('*', function(req, res, next) {
  res.header("Access-Control-Allow-Origin", "*");
  res.header("Access-Control-Allow-Headers", "X-Requested-With");
  res.header("Access-Control-Allow-Methods","PUT,POST,GET,DELETE,OPTIONS");
  res.header("X-Powered-By",' 3.2.1')
  res.header("Content-Type", "application/json;charset=utf-8");
  next();
});

http.createServer({}, app).listen({ port: 8080, host: '0.0.0.0' }, () => {
  console.log('Server listening at http://127.0.0.1:8080/')
})

// 获取应用列表
app.get('/getAppList', (req, res) => {
  let appList = [
    { id: 1, name: 'test1' },
    { id: 2, name: 'test2' },
  ]
  res.status(200).send(appList);
});

```