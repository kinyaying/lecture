.
├── README.md         自述文件，技术说明
├── README.me         自述文件，文件结构
├── api               server和front共用的api模块
│   ├── README.md
│   ├── accountApi.js
│   ├── baseApi.js
│   ├── index.js      api 入口，新的api需要在这注册
│   ├── orderApi.js
│   ├── poiApi.js
│   └── productApi.js
├── config
│   ├── defaults.json
│   ├── env
│   │   ├── config.dev.json
│   │   ├── config.local.json
│   │   └── config.prod.json
│   ├── index.js      webpack配置文件（基础配置）
│   ├── overrides.json
│   └── webpack
│       ├── default.js
│       ├── index.js
│       ├── loader
│       │   ├── html-loader
│       │   │   ├── CHANGELOG.md
│       │   │   ├── LICENSE
│       │   │   ├── README.md
│       │   │   ├── index.js
│       │   │   ├── lib
│       │   │   │   └── attributesParser.js
│       │   │   └── package.json
│       │   └── template-loader
│       │       ├── README.md
│       │       ├── package.json
│       │       └── src
│       │           ├── index.js
│       │           └── rule.js
│       ├── local.js
│       ├── module
│       │   └── buildHelper
│       │       └── index.js
│       └── prod.js
├── deploy            项目发布相关 (pm2 startOrGracefulReload ./deploy/pm2.json --update-env)
│   ├── build.sh
│   ├── check.sh
│   ├── deploy.sh
│   ├── manifest.yaml
│   └── pm2.json
├── docs
│   └── todos.md      
├── front             项目代码
│   ├── client
│   │   ├── App.vue   根组件
│   │   ├── component 项目组件
│   │   │   ├── ErrorTipPage.vue
│   │   │   ├── OrderCard.vue
│   │   │   ├── ProductCard.vue
│   │   │   ├── ProgressState.vue
│   │   │   └── Tab.vue
│   │   ├── pages     页面级组件
│   │   │   ├── order
│   │   │   │   ├── AsyncExport.vue
│   │   │   │   ├── Export.vue
│   │   │   │   └── List.vue
│   │   │   └── product
│   │   │       ├── Create.vue
│   │   │       ├── Delete.vue
│   │   │       ├── Modify.vue
│   │   │       ├── Process.vue
│   │   │       ├── ProductList.vue
│   │   │       └── ShoppingBag.vue
│   │   ├── router.js   前端路由（history-router）
│   │   └── utils
│   │       ├── browser.js
│   │       ├── mss.js
│   │       └── tools.js
│   ├── common          工具
│   │   ├── api.js      基于http模块，将http注入API中
│   │   ├── http.js     axios封装的http请求模块
│   │   ├── template.js vue根实例，入口
│   │   └── upload.js
│   ├── component       公共组件
│   │   └── NavMenu.vue
│   ├── entry           
│   │   ├── 404.js
│   │   ├── index.js    SPA页面入口，执行template()
│   │   ├── login.js    login页面
│   │   ├── pc
│   │   │   └── index.js
│   │   └── upload.js
│   ├── layout          .art模板文件
│   │   ├── base.art    
│   │   └── pc
│   │       └── act.art
│   ├── page
│   │   ├── 404.html
│   │   ├── index.art   index模板文件，继承base.art
│   │   ├── login.art   login模板文件，继承base.art
│   │   ├── pc
│   │   │   └── index.art
│   │   ├── redirect.art
│   │   └── upload.art
│   └── static          静态资源目录
│       ├── css
│       │   ├── 404.css
│       │   └── pc
│       │       └── act
│       │           └── poiNewCustomer
│       │               └── new.css
│       └── img
│           └── pc
│               ├── ARM�\236��\236\204�\233�-cheatsheetv1-1920x1080.png
│               └── freego_logo.png
├── nodemon.json                  nodemon配置
├── package-lock.json
├── package.json                  项目配置文件
├── server                        服务相关
│   ├── api
│   │   ├── index.js              server端使用的axios实例
│   │   └── request.js            
│   ├── index.js                  server端入口
│   ├── middleware
│   │   ├── authorize
│   │   │   └── index.js
│   │   ├── devMiddleware
│   │   │   ├── index.js
│   │   │   └── koa-webpack-dev-middleware
│   │   │       ├── README.md
│   │   │       └── index.js
│   │   ├── errHandler
│   │   │   └── index.js
│   │   ├── mssSts
│   │   │   └── index.js
│   │   ├── mta
│   │   │   ├── index.js
│   │   │   └── utils.js
│   │   ├── pathModify
│   │   │   └── index.js
│   │   ├── perf
│   │   │   └── index.js
│   │   ├── proxy
│   │   │   └── index.js
│   │   └── router
│   │       ├── auth
│   │       │   └── index.js
│   │       ├── index.js
│   │       ├── monitor
│   │       │   └── index.js
│   │       ├── other.js
│   │       ├── page
│   │       │   └── index.js
│   │       ├── routerFilter.js
│   │       ├── static
│   │       │   └── index.js
│   │       └── utils.js
│   └── modules
│       ├── appErrHandler
│       │   └── index.js
│       ├── callback
│       │   └── index.js
│       ├── epassport
│       │   ├── api.js
│       │   └── index.js
│       ├── koa-proxies
│       │   ├── examples
│       │   │   ├── package.json
│       │   │   ├── server.js
│       │   │   └── statics
│       │   │       └── index.html
│       │   ├── index.js
│       │   └── readme.md
│       ├── logger
│       │   └── index.js
│       ├── mcc
│       │   ├── index.js
│       │   └── mcc.js
│       └── mss
│           └── index.js
├── var
│   └── sankuai
│       └── logs
│           └── reco_fe_freego_amdin
└── webpack.config.js     webpack入口
