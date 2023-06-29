Pattern: Missing use of `=` for default value

Issue: -

## Description

**DO** use `=` to separate a named parameter from its default value.

Example of **incorrect** code:
```dart
m({a: 1})
```

Example of **correct** code:
```dart
m({a = 1})
```

## Further Reading

* [Linter for Dart - prefer_equal_for_default_values](https://dart.dev/tools/linter-rules/prefer_equal_for_default_values)
* [Effective Dart](https://dart.dev/guides/language/effective-dart/usage)