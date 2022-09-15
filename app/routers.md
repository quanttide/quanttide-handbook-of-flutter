# 页面路由

使用官方推荐的[`go_router`](https://gorouter.dev)库。

## 定义路由

根据`go_router`文档对[声明式路由](https://gorouter.dev/declarative-routing)的说明配置，如：

```dart
import 'package:go_router/go_router.dart';

/// 页面路由
final GoRouter router = GoRouter(
  routes: <GoRoute>[
    // 首页
    GoRoute(
      path: '/',
      builder: (BuildContext context, GoRouterState state) {
        return HomeScreen();
      },
    ),
    // 其他页面
    ...
  ]
)
```

## 配置入口类

在[入口文件`lib/main.dart`](app/main.md)导入路由类

```dart
import 'router.dart';
```

配置[入口类](app/main.md)

```dart
MaterialApp.router(
    ...
    /// 路由
    routeInformationProvider: router.routeInformationProvider,
    routeInformationParser: router.routeInformationParser,
    routerDelegate: router.routerDelegate,
    ...
)
```

## 切换为History模式

```dart

```

## 其他社区库

- [`fluro`](https://pub.dev/packages/fluro)
- [`auto_route`](https://pub.dev/packages/auto_route)
