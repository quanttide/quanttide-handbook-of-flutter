# RESTful标准URL设置

目前在社区找到的方案，都不是标准RESTful实现，不过比较方便可以支持定制成RESTful。

- [fluro](https://pub.dev/packages/fluro)：从文档上看支持类似于`/users/:id`的特性，可以满足RESTful的URLPattern的基本要求。
- [auto_route](https://pub.dev/packages/auto_route)：看起来更加复杂，搞不清可以搞成什么样。看[源码的example](https://github.com/Milad-Akarie/auto_route_library/blob/master/auto_route/example/lib/web/router/web_router.dart)可以搞同样的特性。

一方面，还需要继续蹲方案，找到RESTful的合适方案。另一方面，还不清楚如何在这两个方案中做选择，还需要搞清楚，在阅读、讨论和实践中逐渐明确。