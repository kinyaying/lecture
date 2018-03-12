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
=======
bodyparser
- 模板 ejs
- koa的模型 洋葱模型 （类比：双向链表结构）
https://segmentfault.com/a/1190000007468153
2、扫码购B端项目的整体结构
wiki
树形图 []
流程图 []
流程图：
webpack
front
delpoy(shell)

3、扫码购登录模块的介绍
  3.1 页面跳转登录方式

  3.2 iframe嵌入登录框方式

  3.3 epassport登录框的定制化设置

  3.4 总结
  两种方式的优缺点
  iframe 优点：
  能够调整登录界面的样式，对开发者来说自由度更大
  缺点：
  流程相对复杂

  页面跳转方式：
  优点：
  实现简单
  缺点：
  UI界面是第三方提供，具有局限性。如果对登录界面有样式需求，无法实现

4、路由部分的结构调整
5、UUID的设计

6、遇到的问题
1、next(); return next(); await next();
2、静态资源前置
3、清除cookie，再次登录时出现token失效的问题
4、user 没有初始值 报错的问题
7、Q&A
3、侧边栏bugfix
