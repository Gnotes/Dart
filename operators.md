# 特殊语法操作符

> 只讲重点（就是自己懵逼的）

## `??` 赋值操作符

```dart
b ??= value; // 如果 b 是 null，则赋值 value 给 b；否则不做任何更改
```

## `..` 链式调用操作符

> 注意： 严格来说， 两个点的级联语法不是一个操作符。 只是一个 Dart 特殊语法

```dart
querySelector('#button') // 获取对象
  ..text = 'Confirm'     // 设置属性
  ..classes.add('important') // 添加类
  ..onClick.listen((e) => window.alert('Confirmed!')); // 添加事件
```

## `?.` 条件成员访问

例如 foo?.bar 如果 foo 为 null 则返回 null，否则返回 bar 成员
