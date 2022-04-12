# 页面路由设置

Web网站是以单页应用的形式上线的，要让它看起来像普通网页，可以用网址访问到具体资源，修改路由必不可少。

## 选型

[`fluro`](https://pub.dev/packages/fluro)：从文档上看支持类似于`/users/:id`的特性，可以满足RESTful的URLPattern的基本要求。fluro更简单，且已经能够满足需求。

其他备选：

- [`auto_route`](https://pub.dev/packages/auto_route)：看起来更加复杂，搞不清可以搞成什么样。看[源码的example](https://github.com/Milad-Akarie/auto_route_library/blob/master/auto_route/example/lib/web/router/web_router.dart)可以搞同样的特性。

小结：

- 目前在社区找到的方案，都不是标准RESTful实现，不过比较方便可以支持定制成RESTful。
