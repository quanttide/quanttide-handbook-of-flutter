# RESTful标准URL设置

目前在社区找到的方案，都不是标准RESTful实现，不过比较方便可以支持定制成RESTful。

- [fluro](https://pub.dev/packages/fluro)：从文档上看支持类似于`/users/:id`的特性，可以满足RESTful的URLPattern的基本要求。
- [auto_route](https://pub.dev/packages/auto_route)：看起来更加复杂，搞不清可以搞成什么样。看[源码的example](https://github.com/Milad-Akarie/auto_route_library/blob/master/auto_route/example/lib/web/router/web_router.dart)可以搞同样的特性。

一方面，还需要继续蹲方案，找到RESTful的合适方案。另一方面，还不清楚如何在这两个方案中做选择，还需要搞清楚，在阅读、讨论和实践中逐渐明确。

[Updated in 2021-10-20]

- fluro更简单，且已经能够满足需求，初步计划使用fluro。
- Flutter for Web作为SPA在部署静态网站时[有问题](https://cloud.tencent.com/document/product/436/56555#.E9.9D.99.E6.80.81.E7.BD.91.E7.AB.99.E5.8A.9F.E8.83.BD.E9.85.8D.E5.90.88.E5.89.8D.E7.AB.AF-vue-.E6.A1.86.E6.9E.B6.E4.B8.80.E8.B5.B7.E4.BD.BF.E7.94.A8.EF.BC.8C.E5.BD.93.E8.B7.AF.E7.94.B1.E8.AE.BE.E7.BD.AE.E4.B8.BA-history-.E6.A8.A1.E5.BC.8F.EF.BC.8C.E5.88.B7.E6.96.B0.E9.A1.B5.E9.9D.A2.E9.81.87.E5.88.B0404.E9.97.AE.E9.A2.98.E6.80.8E.E4.B9.88.E5.8A.9E.EF.BC.9F)，已经解决。
