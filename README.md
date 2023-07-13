### 1、DB

采用mongoDB数据库，由[MongoDB Cloud](https://www.mongodb.com/cloud)托管.


### 2、子应用

#### 2.1、[honeycomb-server](https://github.com/guanweisong/honeycomb-server.serverless)

> 通过prisma操作mongoDB，对外提供restful形式的api接口。在模块设计上与[Wordpress](https://wordpress.org/)模块结构类似。

技术栈：

* [Next.js](https://nextjs.org/)
* [Typescript](https://www.typescriptlang.org/)

MODEL划分：

* `category`：文章分类
* `comment`：用户评论
* `link`：友情链接
* `media`：媒体中心
* `page`：页面
* `post`：文章
* `setting`：设置
* `tag`：标签
* `user`：用户
* `token`：token

安全防护：
* 所有接口使用节流中间件
* 关键接口使用行为验证码拦截，例如登陆接口，用户发表评论接口等
* 用户权限采用JWT签名验证
* HTTP接口传输采用SSL加密

> 由[Vercel](https://vercel.com/)托管

#### 2.2、[honeycomb-admin](https://github.com/guanweisong/honeycomb-admin)

> 通过[honeycomb-server](https://github.com/guanweisong/honeycomb-server)提供的restful api实现的SPA网站管理平台。

技术栈：

* [React](https://reactjs.org/)
* [Next.js](https://umijs.org/)
* [Hox](https://github.com/umijs/hox)
* [AntD](https://ant.design/)
* [Typescript](https://www.typescriptlang.org/)
* [Ant Design Pro](https://pro.ant.design/)
* [Tailwindcss](https://tailwindcss.com)

> 由[Vercel](https://vercel.com/)托管

#### 2.3、[honeycomb-wap](https://github.com/guanweisong/honeycomb-wap)

> 通过[honeycomb-server](https://github.com/guanweisong/honeycomb-server)提供的restful api实现的移动/PC端纯静态应用

技术栈：

* [React](https://reactjs.org/)
* [Next.js](https://nextjs.org/)
* [Ant Design Mobile](https://mobile.ant.design)
* [Typescript](https://www.typescriptlang.org/)
* [SWR](https://swr.vercel.app)
* [Tailwindcss](https://tailwindcss.com)

> 由[Vercel](https://vercel.com/)托管

### 3、第三方远程组件

#### 3.1、人机验证码

由[腾讯防水墙](https://007.qq.com)提供

#### 3.2、对象存储

由[腾讯云COS](https://cloud.tencent.com/product/cos)提供
