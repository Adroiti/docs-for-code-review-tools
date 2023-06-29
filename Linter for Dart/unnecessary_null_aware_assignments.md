Pattern: Unnecessary null-aware assignment

Issue: -

## Description

Using `null` on the right-hand side of a null-aware assignment effectively makes the assignment redundant.

Example of **correct** code:
```dart
var x;
x ??= 1;
```

Example of **incorrect** code:
```dart
var x;
x ??= null;
```

## Further Reading

* [Linter for Dart - unnecessary_null_aware_assignments](https://dart.dev/tools/linter-rules/unnecessary_null_aware_assignments)