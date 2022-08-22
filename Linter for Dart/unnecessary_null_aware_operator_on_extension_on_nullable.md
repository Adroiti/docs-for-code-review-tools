Pattern: Unnecessary null-aware operator

Issue: -

## Description

Avoid null aware operators for members defined in an extension on a nullable type.

Example of **incorrect** code:

```dart
extension E on int? {
 int m() => 1;
}
f(int? i) => i?.m();
```

Example of **correct** code:

```dart
extension E on int? {
 int m() => 1;
}
f(int? i) => i.m();
```

## Further Reading

* [Linter for Dart - unnecessary_null_aware_operator_on_extension_on_nullable](https://dart-lang.github.io/linter/lints/unnecessary_null_aware_operator_on_extension_on_nullable.html)