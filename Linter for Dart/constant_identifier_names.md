Pattern: Invalid constant identifier name

Issue: -

## Description

In new code, use `lowerCamelCase` for constant variables, including enum values.

In existing code that uses `ALL_CAPS_WITH_UNDERSCORES` for constants, you may
continue to use all caps to stay consistent.

Example of **correct** code:
```dart
const pi = 3.14;
const defaultTimeout = 1000;
final urlScheme = new RegExp('^([a-z]+):');

class Dice {
 static final numberGenerator = new Random();
}
```

Example of **incorrect** code:
```dart
const PI = 3.14;
const kDefaultTimeout = 1000;
final URL_SCHEME = new RegExp('^([a-z]+):');

class Dice {
 static final NUMBER_GENERATOR = new Random();
}

```

## Further Reading

* [Linter for Dart - constant_identifier_names](https://dart-lang.github.io/linter/lints/constant_identifier_names.html)