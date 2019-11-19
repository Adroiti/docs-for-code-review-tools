Pattern: Use of `double`/`int` check

Issue: -

## Description

When compiled to JS, integer values are represented as floats. That can lead to
some unexpected behavior when using either `is` or `is!` where the type is
either `int` or `double`.

Example of **incorrect** code:
```dart
f(num x) {
 if (x is double) {
  ...
 } else if (x is int) {
  ...
 }
}
```

Example of **correct** code:
```dart
f(dynamic x) {
 if (x is num) {
  ...
 } else {
  ...
 }
}
```

## Further Reading

* [Linter for Dart - avoid_double_and_int_checks](https://dart-lang.github.io/linter/lints/avoid_double_and_int_checks.html)