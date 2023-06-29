Pattern: Missing use of raw string

Issue: -

## Description

A raw string can be used to avoid escaping only backslashes and dollars.

Example of **incorrect** code:
```dart
var s = 'A string with only \\ and \$';
```

Example of **correct** code:
```dart
var s = r'A string with only \ and $';
```

## Further Reading

* [Linter for Dart - use_raw_strings](https://dart.dev/tools/linter-rules/use_raw_strings)