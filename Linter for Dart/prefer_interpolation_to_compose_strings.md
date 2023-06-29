Pattern: Missing use of interpolation to compose strings

Issue: -

## Description

Using interpolation when composing strings and values is usually easier to write and read than concatenation.

Example of **incorrect** code:
```dart
'Hello, ' + name + '! You are ' + (year - birth) + ' years old.';
```

Example of **correct** code:
```dart
'Hello, $name! You are ${year - birth} years old.';
```

## Further Reading

* [Linter for Dart - prefer_interpolation_to_compose_strings](https://dart.dev/tools/linter-rules/prefer_interpolation_to_compose_strings)