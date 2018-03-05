1、koa的简单介绍
- koa [https://koa.bootcss.com/]
- 运行koa服务
```
const Koa = require('koa');
const app = new Koa();
app.listen(function(){ ... }, 3000);
```
- 路由 怎么配置页面 [https://www.npmjs.com/package/koa-router]
koa-router
```
var Koa = require('koa');
var Router = require('koa-router');

var app = new Koa();
var router = new Router();

router.get('/', (ctx, next) => {
  // ctx.router available
});

app
  .use(router.routes())
  .use(router.allowedMethods());
```

- 中间件 [https://www.jianshu.com/p/a30c193f6e61]

- ctx 的构成 [https://github.com/koajs/koa/blob/master/docs/api/context.md]
- 模板 ejs

2、扫码购B端项目的整体结构
wiki
树形图 []
流程图 []

3、扫码购登录模块的介绍
  3.1 SSO登录的流程(页面跳转登录方式)
  3.2 iframe登录方式
  总结两种方式的优缺点
  3.2 登录的流程图
4、路由部分的结构调整
5、UUID的设计
6、Q&A 遇到的问题
1、next(); return next(); await next();
2、静态资源前置
3、

https://freegoe.waimai.dev.sankuai.com/epassport/callback?cb=http%3A%2F%2Ffreegoe.waimai.dev.sankuai.com%2Fredirect.html&BSID=pjbqutlDRAZL0D4jUXCIK0cPczq-h9zYvb0lNbQ6G1lGWPTZ_dr1jbK42zO_xfmEdTjZ5DM5wkrOlJj0DqrLyQ 的网页可能暂时无法连接，或者它已永久性地移动到了新网址。
