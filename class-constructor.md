# 类与构造

> 在 **Dart2** 中 关键字 `new` 是可选的.

```dart
class Point {
  num x; // 声明x并初始化为 null
  num y;
  num z;

  // 构造函数: 和类名字一样的方法
  Point(num x, num y){
      this.x = x;
      this.y = y;
  }
  // 构造语法糖，等同上边构造
  // Point(this.x, this.y);

  Point.fromJson(Map json){
      x = json['x'];
      y = json['y'];
  }

  // 构造参数列表后的冒号 ⚠️ ，冒号后: { 左大括号前 中间的代码会优先与构造执行，因此可以用于参数初始化，父类构造调用
  // Point(num p): z = p {
  //     print('this.z = $z');
  // }
}

void main(){
    var point1 = new Point(1,2);
    var point2 = new Point.fromJson({"x":1, "y":2});
    var point3 = Point.fromJson({"x":1, "y":2}); // 没有使用new 关键字一样可以 ？

    print(point1.x);
    print(point2.x);
    print(point3.x);
}
```

## 语法点

- 构造函数: 和类名字一样的方法
- 构造语法糖: 如Point构造 `Point(this.x, this.y);`
- 如果 _没有定义构造，会存在一个 **无参** 的构造，并会 **自动** 调用父类 **无参** 构造_
- _构造函数不会继承_，因此需要显示调用父类构造
- 命名构造函数: 用于实现多个构造或明确构造语义，如 `Point.fromJson(Map json){...}`，通过语法： `类名称.命名构造名称(参数列表){}` 指定命名构造函数，一个类只能定义一个默认的构造，但是可以定义多个命名构造
- **`构造函数参数后边的冒号(:)`**，冒号后 **`:` `{` 左大括号前 中间的代码会优先与构造执行，因此可以用于参数初始化，父类构造调用**，如上 _Point(num p): `z = p` {}_，其中 `z = p` 这段代码就会先与构造执行
- 常量构造，使用的时候可以使用 const 替代 new，并且构造内所有属性都必须是 final
  ```dart
  class Point {
      final num z;
      const Point(this.z);
  }

  void main(){
      var p = const Point(1);
  }
  ```
- setter & getter: 定义属性的取值赋值操作
- abstract : 定义抽象类或接口
- implements: 实现接口
- extends: 继承单个类
- with: 实现多继承

```dart
// with 多继承
class Maestro extends Person with Musical, Aggressive, Demented {
    
}
```

```dart
class Color {
  static const red = const Color('red'); // 静态变量
  final String name;      // 实例属性
  const Color(this.name); // 常量构造
}
```