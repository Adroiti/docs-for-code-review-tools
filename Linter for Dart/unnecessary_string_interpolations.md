Pattern: Unnecessary string interpolation

Issue: -

## Description

Don't use string interpolation if there's only a string expression in it.

Example of **incorrect** code:
```dart
String message;
String o = '$message';
```

Example of **correct** code:
```dart
String message;
String o = message;
```

## Further Reading

* [Linter for Dart - unnecessary_string_interpolations](https://dart.dev/tools/linter-rules/unnecessary_string_interpolations)