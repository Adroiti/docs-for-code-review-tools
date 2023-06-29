Pattern: Missing use of null-aware operator

Issue: -

## Description

Prefer using null-aware operators instead of null checks in conditional expressions.

Example of **incorrect** code:
```dart
v = a == null ? null : a.b;
```

Example of **correct** code:
```dart
v = a?.b;
```

## Further Reading

* [Linter for Dart - prefer_null_aware_operators](https://dart.dev/tools/linter-rules/prefer_null_aware_operators)