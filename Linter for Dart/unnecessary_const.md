Pattern: Unnecessary `const`

Issue: -

## Description

**AVOID** repeating const keyword in a const context.

Example of **incorrect** code:
```dart
class A { const A(); }
m(){
 const a = const A();
 final b = const [const A()];
}
```

Example of **correct** code:
```dart
class A { const A(); }
m(){
 const a = A();
 final b = const [A()];
}
```

## Further Reading

* [Linter for Dart - unnecessary_const](https://dart-lang.github.io/linter/lints/unnecessary_const.html)