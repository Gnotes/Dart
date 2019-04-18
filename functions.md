# 函数

> 方法也是对象并且具有一种 类型， `Function`.

```dart
返回值类型 方法名称( 参数类型 参数列表, ...){

}
// 如 位置参数
void main(List<String> args, ... ){}
// 或 命名参数
void main({List<String> args, ... })
```

## 可选参数

可选参数可以有两种处理方式：
- ① 可选位置参数: 根据函数 `参数位置` 设置参数是否可选
- ② 可选命名参数: 根据函数 `参数名称` 确认参数是否可选

```dart
String say(String from, String msg, [String other, bool upperCase]) {
  
}

say("Dart"," is good.");
say("Dart"," is good.", "very");
```

```dart
String say({String from, String msg, String other, bool upperCase}) {
  
}

say(from: "Dart", msg: " is good."); // 指定参数名称
say(from: "Dart", msg: " is good.", other: "very", upperCase: true);
```

## 默认参数

使用 `命名参数` 形式，通过等号 (`=`) 赋予默认值

```dart
String say({String from, String msg, String other, bool upperCase = false}) {
    var result = '$from $msg ${ other ??= "" } ';
    if(upperCase) return result.toUpperCase();
    return result;
}
  
print(say(from: "Dart", msg: "is good."));
print(say(from: "Dart", msg: "is good.", other: " fast and easy to use.", upperCase: true));

// Dart is good.  
// DART IS GOOD.  FAST AND EASY TO USE. 
```

## 语法点

- Dart也有 `匿名函数`
- 并且存在 `词法作用域`，即 _变量_ 在编写的时候就确定了作用域
- 也存在 `函数闭包`，即 函数不管在哪里被调用，都可以访问函数内部的变量.
- 默认存在返回值 null， 即 `return null;` 
