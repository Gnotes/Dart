# 变量

## 变量声明

```dart
var name = "Dart";
```

## 语法点

- 没有初始化的变量都是 `null`，即是显示指定了类型为数字的变量
    ```dart
    int lineCount;
    assert(lineCount == null);
    ```
- 可选类型：变量类型都是可选的，如果使用 _`var` 声明的变量可以 `类型推断`_
    ```dart
    String name = "Dart";   // 指定类型为字符串
    var fullName = "Dart";  // 推断为字符串
    fullName = 10;          // 错误 ❌ 不能赋值其他类型
    ```
    - 一旦 var 声明的变量推断了类型，就不能再赋值其他类型
- 动态类型：`dynamic`、`Object`，可以赋值不同类型数据给变量
    ```dart
    dynamic age = 1;
    Object weight = 60;

    age = "1 year old";
    weight = "60 KG";

    print(age.length);    // ✅
    print(weight.length); // 错误 ❌ Object 定义的对象上没有length属性
    ```
    - `dynamic` 会给出所有可能的方法或属性，⚠️ 谨慎使用，可能导致运行时错误
    - `Object` 只能使用 Object 上定义的方法或属性
- 常量定义：`final`、`const`
    ```dart
    final name = "Dart";
    const Pi = 3.14;
    // final 和 const 可以不指定类型
    // final String fullName = "Dart";
    // const double Pi = 3.14;
    ```
    - final 和 const 可以不指定类型，但同样会推到出类型
    - final 和 const 区别在于 final 为 **运行时** 赋值，而const 是 **编译时** 赋值，而最大区别在于 _**值为对象时**_，final 的对象可以修改对象的 `内部` 的值
        ```dart
        final arr1 = [1,2,3];
        const arr2 = [1,2,3];
        arr1.add(2);
        arr2.add(2); // 错误 ❌ 不能修改 const 声明的值
        ```