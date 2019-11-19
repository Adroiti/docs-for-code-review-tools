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

* [Linter for Dart - prefer_equal_for_default_values](https://dart-lang.github.io/linter/lints/prefer_equal_for_default_values.html)
* [Effective Dart](https://dart.dev/guides/language/effective-dart/usage)