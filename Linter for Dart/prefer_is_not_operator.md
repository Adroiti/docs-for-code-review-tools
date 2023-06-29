Pattern: Missing use of `is!`

Issue: -

## Description

When checking if an object is not of a specified type, it is preferable to use the `is!` operator.

Example of **incorrect** code:
```dart
if (!(foo is Foo)) {
 ...
}
```

Example of **correct** code:
```dart
if (foo is! Foo) {
 ...
}
```

## Further Reading

* [Linter for Dart - prefer_is_not_operator](https://dart.dev/tools/linter-rules/prefer_is_not_operator)