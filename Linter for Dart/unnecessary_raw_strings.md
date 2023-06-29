Pattern: Unnecessary raw string

Issue: -

## Description

Use raw string only when needed.

Example of **incorrect** code:

```dart
var s1 = r'a';
```

Example of **correct** code:

```dart
var s1 = 'a';
var s2 = r'$a';
var s3 = r'\a';
```

## Further Reading

* [Linter for Dart - unnecessary_raw_strings](https://dart.dev/tools/linter-rules/unnecessary_raw_strings)