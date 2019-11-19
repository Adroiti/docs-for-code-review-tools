Pattern: Use of `print`

Issue: -

## Description

**DO** avoid `print` calls in production code.

Example of **incorrect** code:
```dart
void f(int x) {
 print('debug: $x');
 ...
}
```

## Further Reading

* [Linter for Dart - avoid_print](https://dart-lang.github.io/linter/lints/avoid_print.html)