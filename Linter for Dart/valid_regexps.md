Pattern: Invalid regular expression

Issue: -

## Description

Regular expressions created with invalid syntax will throw a `FormatException` at runtime so should be avoided.

Example of **incorrect** code:
```dart
print(RegExp('(').hasMatch('foo()'));
```

Example of **correct** code:
```dart
print(RegExp('[(]').hasMatch('foo()'));
```

## Further Reading

* [Linter for Dart - valid_regexps](https://dart-lang.github.io/linter/lints/valid_regexps.html)