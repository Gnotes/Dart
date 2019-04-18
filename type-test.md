# 类型检测

| 操作符 | 解释 |
| - | - |
| as | 类型转换 |
| is | 如果对象是指定的类型返回 True |
| is! | 如果对象是指定的类型返回 False |

```dart
if (emp is Person) {
  emp.firstName = 'Bob';
}
```

```dart
(emp as Person).firstName = 'Bob';
```

> 注意： 上面这两个代码效果是有区别的。如果 emp 是 null 或者不是 Person 类型， 则第一个示例使用 is 则不会执行条件里面的代码，而第二个情况使用 as 则会抛出一个异常