Pattern: Missing use of null-aware method call

Issue: -

## Description

Instead of checking nullability of a function/method `f` before calling it you can use `f?.call()`.

Example of **incorrect** code:

```dart
if (f != null) f!();
```

Example of **correct** code:

```dart
f?.call();
```

## Further Reading

* [Linter for Dart - prefer_null_aware_method_calls](https://dart-lang.github.io/linter/lints/prefer_null_aware_method_calls.html)