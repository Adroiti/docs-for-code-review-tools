Pattern: Missing use of if-null for bool

Issue: -

## Description

Use if-null operators to convert nulls to bools.

Example of **incorrect** code:

```dart
if (nullableBool == true) {
}
if (nullableBool != false) {
}
```

Example of **correct** code:

```dart
if (nullableBool ?? false) {
}
if (nullableBool ?? true) {
}
```

## Further Reading

* [Linter for Dart - use_if_null_to_convert_nulls_to_bools](https://dart.dev/tools/linter-rules/use_if_null_to_convert_nulls_to_bools)