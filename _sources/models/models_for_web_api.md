# 网络API返回值数据模型

这篇文章讲设计数据模型的方法，以自建的云开发SDK为例。

## 为什么使用自建Model类代替Map

思路来源于：https://book.flutterchina.club/chapter11/json_model.html。

> 这意味着直到运行时我们才知道值的类型。 通过这种方法，我们失去了大部分静态类型语言特性：类型安全、自动补全和最重要的编译时异常。这样一来，我们的代码可能会变得非常容易出错。例如，当我们访问name或email字段时，我们输入的很快，导致字段名打错了。但由于这个 JSON 在 map 结构中，所以编译器不知道这个错误的字段名，所以编译时不会报错。

因此，我们可以通过定义Model类的方法，在创建属性时约定类型，这样便可以不损失静态类型语言的特性。

> 具体做法就是，通过预定义一些与 Json 结构对应的 Model 类，然后在请求到数据后再动态根据数据创建出 Model 类的实例。这样一来，在开发阶段我们使用的是 Model 类的实例，而不再是 Map/List，这样访问内部属性时就不会发生拼写错误。

## 设计Model类的结构

Model的抽象类需要以下定义三个方法：

- 构造器。传入属性。
- fromMap构造器。传入Map类型转Model
- toMap方法。把Model转成Map类型。

## 跨组件使用Model类

需要用Provider改造。

方法详见：https://book.flutterchina.club/chapter7/provider.html#_7-3-1-provider。