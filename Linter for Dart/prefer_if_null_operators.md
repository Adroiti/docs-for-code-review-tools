Pattern: Missing use of if null operator

Issue: -

## Description

Prefer using if null operators instead of null checks in conditional expressions.

Example of **incorrect** code:
```dart
v = a == null ? b : a;
```

Example of **correct** code:
```dart
v = a ?? b;
```

## Further Reading

* [Linter for Dart - prefer_if_null_operators](https://dart.dev/tools/linter-rules/prefer_if_null_operators)