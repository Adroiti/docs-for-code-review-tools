Pattern: Use of shadowing type parameter

Issue: -

## Description

**AVOID** shadowing type parameters.

Example of **incorrect** code:
```dart
class A<T> {
 void fn<T>() {}
}
```

Example of **correct** code:
```dart
class A<T> {
 void fn<U>() {}
}
```

## Further Reading

* [Linter for Dart - avoid_shadowing_type_parameters](https://dart-lang.github.io/linter/lints/avoid_shadowing_type_parameters.html)