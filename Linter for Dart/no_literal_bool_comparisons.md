Pattern: Use of literal bool comparison

Issue: -

## Description

**DON'T** use `true` or `false` in equality operations.

This lint applies only if the expression is of a non-nullable `bool` type.

Example of **incorrect** code:
```dart
if (someBool == true) {
}
while (someBool == false) {
}
```

Example of **correct** code:
```dart
if (someBool) {
}
while (!someBool) {
}
```

## Further Reading

* [Linter for Dart - no_literal_bool_comparisons](https://dart-lang.github.io/linter/lints/no_literal_bool_comparisons.html)