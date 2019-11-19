Pattern: Use of void `async`

Issue: -

## Description

When declaring an async method or function which does not return a value,
declare that it returns `Future<void>` and not just void.

Example of **incorrect** code:
```dart
void f() async {}
void f2() async => null;
```

Example of **correct** code:
```dart
Future<void> f() async {}
Future<void> f2() async => null;
```

## Further Reading

* [Linter for Dart - avoid_void_async](https://dart-lang.github.io/linter/lints/avoid_void_async.html)