Pattern: Missing use of `intValue.isOdd`/`isEven`

Issue: -

## Description

**PREFER** the use of `intValue.isOdd`/`isEven` to check for evenness.

Example of **incorrect** code:

```dart
bool isEven = 1 % 2 == 0;
bool isOdd = 13 % 2 == 1;
```

Example of **correct** code:

```dart
bool isEven = 1.isEven;
bool isOdd = 13.isOdd;
```

## Further Reading

* [Linter for Dart - use_is_even_rather_than_modulo](https://dart-lang.github.io/linter/lints/use_is_even_rather_than_modulo.html)