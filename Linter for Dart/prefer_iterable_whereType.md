Pattern: Missing use of `iterable.whereType<T>()`

Issue: -

## Description

**PREFER** `iterable.whereType<T>()` over `iterable.where((e) => e is T)`.

Example of **incorrect** code:
```dart
iterable.where((e) => e is MyClass)
```

Example of **correct** code:
```dart
iterable.whereType<MyClass>()
```

## Further Reading

* [Linter for Dart - prefer_iterable_whereType](https://dart.dev/tools/linter-rules/prefer_iterable_whereType)