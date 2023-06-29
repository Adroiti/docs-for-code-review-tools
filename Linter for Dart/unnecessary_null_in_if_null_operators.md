Pattern: Unnecessary `null` in `if null`

Issue: -

## Description

Using `null` in an `if null` operator is redundant, regardless of which side `null` is used on.

Example of **correct** code:
```dart
var x = a ?? 1;
```

Example of **incorrect** code:
```dart
var x = a ?? null;
var y = null ?? 1;
```

## Further Reading

* [Linter for Dart - unnecessary_null_in_if_null_operators](https://dart.dev/tools/linter-rules/unnecessary_null_in_if_null_operators)