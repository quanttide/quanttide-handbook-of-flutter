# 修改Web应用URL策略

## Flutter应用设置

[官方文档](https://flutter.dev/docs/development/ui/navigation/url-strategies)定义了两种模式：
- Hash模式：默认模式，带有"#"。
- Path模式：不带有"#"。

我们需要把默认的Hash模式改为更符合正常认知的Path模式。

最简单的办法是使用[url_strategies](https://pub.dev/packages/url_strategy)库完成。安装库以后如下使用：

```dart
import 'package:url_strategy/url_strategy.dart';

void main() {
  // Here we set the URL strategy for our web app.
  // It is safe to call this function when running on mobile or desktop as well.
  setPathUrlStrategy();
  runApp(MyApp());
}
```

关键是`setPathUrlStrategy()`，效果等同于官方文档的方法，并且不影响Mobile和Desktop应用。


## 云端部署设置

但这个方法有一个问题是，只允许`web/index.html`的`<base>`标签配置绝对路径而**不允许相对路径**。这会为云端环境部署时带来新的问题。

在云开发的静态网站部署中，由于一个环境提供一个存储桶，根目录是根目录，如果Flutter for Web应用没有在此环境的根目录下，则Flutter for Web应用无法正常运行。在本地时，只需要简单设置为`/`即可，而在云端则需要是`<folder_name>/`，这会不一致。

有两种可能的思路：
1. 想办法让云端配置在本地可以正常运行。
2. 设法写JS传入路径，让本地和云端使用不同的配置，以保证兼容性。
3. 联系云开发静态网站团队商议解决办法。

