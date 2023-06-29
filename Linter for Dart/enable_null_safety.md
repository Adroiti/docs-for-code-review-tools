Pattern: Missing use of sound null safety

Issue: -

## Description

**DO** use sound null safety, by not specifying a dart version lower than `2.12`.

Example of **incorrect** code:
```dart
// @dart=2.8
a() {
}
```

Example of **correct** code:
```dart
b() {
}
```

## Further Reading

* [Linter for Dart - enable_null_safety](https://dart.dev/tools/linter-rules/enable_null_safety)