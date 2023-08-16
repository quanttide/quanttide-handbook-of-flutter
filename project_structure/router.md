# 页面路由

`lib/router.dart`文件。

使用官方推荐的[`go_router`](https://gorouter.dev)库。

使用前先添加库：

```shell
flutter pub add go_router
```

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

## 完整示例

```dart
/// 页面路由和导航栏

import 'package:flutter/material.dart';
import 'package:go_router/go_router.dart';

import './screens/home.dart';
import './screens/course.dart';
import './screens/lecture.dart';
import './screens/learn.dart';
import './screens/mine.dart';
import './screens/settings.dart';


/// 页面路由
final GoRouter router = GoRouter(
  routes: <GoRoute>[
    // 首页
    GoRoute(
      name: 'home',
      path: '/',
      builder: (BuildContext context, GoRouterState state) {
        return AppNav();
      },
    ),
    // 课程页面
    GoRoute(
      name: 'course',
      path: '/courses/:courseName',
      builder: (BuildContext context, GoRouterState state) {
        return CourseScreen(courseName: state.params['courseName']!);
      },
      routes: [
        // 课时页面
        GoRoute(
          name: 'lecture',
          path: 'lectures/:lectureName',
          builder: (BuildContext context, GoRouterState state) {
            return LectureScreen(
              courseName: state.params['courseName']!,
              lectureName: state.params['lectureName']!,
            );
          }
        ),
      ]
    ),
    // 个人中心页面
    GoRoute(
      name: 'mine',
      path: '/mine',
      builder: (BuildContext context, GoRouterState state) {
        return MineScreen();
      }
    ),
    // 设置页面
    GoRoute(
      name: 'settings',
      path: '/settings',
      builder: (BuildContext context, GoRouterState state) {
        return SettingsScreen();
      }
    )
  ],
);
```

## 其他社区库

- [`fluro`](https://pub.dev/packages/fluro)
- [`auto_route`](https://pub.dev/packages/auto_route)
