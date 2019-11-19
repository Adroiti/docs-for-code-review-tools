Pattern: Unnecessary `await` in return

Issue: -

## Description

Avoid returning an awaited expression when the expression type is assignable to the function's return type.

Example of **incorrect** code:
```dart
Future<int> future;
Future<int> f1() async => await future;
Future<int> f2() async {
 return await future;
}
```

Example of **correct** code:
```dart
Future<int> future;
Future<int> f1() => future;
Future<int> f2() {
 return future;
}
```

## Further Reading

* [Linter for Dart - unnecessary_await_in_return](https://dart-lang.github.io/linter/lints/unnecessary_await_in_return.html)