.
├── api
│   ├── index.js            引入api, 实例化api,传入request, 在authorize中被调用
│   └── request.js          使用axios创建请求拦截
├── index.js                程序入口 1、记录访问日志 2、设置session 3、不是local 走授权认证 4、mssSts临时授权 5、API代理 6、添加元信息mta 7、判断nodeEnv，是local 则引入webpack，走开发模式的配置；不是local则添加koa-router 8、起server
├── middleware
│   ├── authorize
│   │   └── index.js        登录逻辑 1、login.html 时，重定向到登录页面 2、拦截Epassport授权成功回调，获取bsid，user，将页面重定向到指定位置或'/' 3、处理退出操作 4、mcc校验，是否需要登录认证，不需要则走下层逻辑 5、若存在用户，则accessTokenHandler，给session绑定accessToken和deviceUUID 6、生成重定向的url，浏览器跳转到指定location
│   ├── devMiddleware
│   │   ├── index.js                    组合并返回webpack中间件（实际项目中未用的）
│   │   └── koa-webpack-dev-middleware  npm上下载的库（做了些修改）
│   │       ├── README.md
│   │       └── index.js
│   ├── errHandler
│   │   └── index.js        处理错误：1、输出日志（端口占用）2、退出进程
│   ├── mssSts
│   │   └── index.js        启用mssSts临时授权中间件
│   ├── mta
│   │   ├── index.js        meta中间件
│   │   └── utils.js
│   ├── pathModify          实际项目未用到
│   │   └── index.js
│   ├── perf                perf监控?
│   │   └── index.js
│   ├── proxy
│   │   └── index.js        API代理请求 proxyReq：设置请求头，写入token, deviceUUID, source, ip 等一些信息，
│   │                                proxyRes：1、解压gzip文件 2、移除返回头中的跨域设置 3、拦截代理请求处理 只要responseCode不是200 就将responseCode写为500处理 4、返回给前端 responseBody
│   └── router
│       ├── index.js        路由入口
│       ├── monitor
│       │   └── index.js    暂时未使用
│       ├── other.js        支持单页面和多页面结构。有.html后缀则为多页面，无后缀则为单页面
│       ├── page
│       │   └── index.js    页面路由，读取对应文件，并给到body返回
│       ├── static
│       │   └── index.js    处理静态资源
│       └── utils.js        工具，提供两个方法：1、getPage 读取页面 2、getFilesWithPath 生成文件路径
└── modules
    ├── appErrHandler       异常处理
    │   └── index.js
    ├── callback            sever的回调函数 1、注册HLB 2、初始化mcc 3、发送信号给PM2
    │   └── index.js
    ├── epassport           在authorize中被调用
    │   ├── api.js          1、token获取用户信息 2、退出SSO中的登录状态，便于后台的API校验
    │   └── index.js        1、生成对应的Epassport登录地址 2、针对koa的回调拦截 3、根据bsid退出当前账户在Epassport的登录状态
    ├── koa-proxies         npm上下载的库(做了部分修改)，起代理作用
    │   ├── examples
    │   │   ├── package.json
    │   │   ├── server.js
    │   │   └── statics
    │   │       └── index.html
    │   ├── index.js      
    │   └── readme.md
    ├── logger
    │   └── index.js        日志相关
    ├── mcc
    │   ├── index.js        checker暴露两个方法：1、needLoginFilter 是否需要需要登录认证 2、needLoginFilter 是否需要获取AccessToken
    │   └── mcc.js          实现一个Store（本地的mcc配置）???
    └── mss
        └── index.js        mssSts临时授权，目前是path为'/msstoken'时走此中间件，给请求的body添加一些信息，如server,link,policy,signature,key,accessid
