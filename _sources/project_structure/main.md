# 入口文件

```dart
import 'package:flutter/material.dart';
import 'package:flutter_web_plugins/url_strategy.dart';

import 'theme.dart';
import 'router.dart';


/// APP入口
void main() async {
  /// 配置APP路由规则
  /// https://docs.flutter.dev/development/ui/navigation/url-strategies
  usePathUrlStrategy();
  /// 运行APP
  runApp(const MyApp());
}

/// APP类，包含APP各项基本设置。
class MyApp extends StatelessWidget {
  const MyApp({super.key});
  
  /// 构建APP
  @override
  Widget build(BuildContext context) {
    return MaterialApp.router(
    /// APP标题
    title: '<your app title>',
    /// APP主题
    theme: defaultThemeData, 
    /// 路由
    routerConfig: router,
    );
  }
}
```
