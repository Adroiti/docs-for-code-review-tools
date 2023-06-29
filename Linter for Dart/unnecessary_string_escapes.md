Pattern: Unnecessary string escape

Issue: -

## Description

Remove unnecessary backslashes in strings.

Example of **incorrect** code:

```dart
'this string contains 2 \"double quotes\" ';
"this string contains 2 \'single quotes\' ";
```

Example of **correct** code:

```dart
'this string contains 2 "double quotes" ';
"this string contains 2 'single quotes' ";
```

## Further Reading

* [Linter for Dart - unnecessary_string_escapes](https://dart.dev/tools/linter-rules/unnecessary_string_escapes)