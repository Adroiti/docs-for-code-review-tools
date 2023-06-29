Pattern: Use of `null` return

Issue: -

## Description

Functions that return primitive types such as `bool`, `double`, `int`, and `num` are
generally expected to return non-nullable values. Thus, returning null where a
primitive type was expected can lead to runtime exceptions.

Example of **incorrect** code:
```dart
bool getBool() => null;
num getNum() => null;
int getInt() => null;
double getDouble() => null;
```

Example of **correct** code:
```dart
bool getBool() => false;
num getNum() => -1;
int getInt() => -1;
double getDouble() => -1.0;
```

## Further Reading

* [Linter for Dart - avoid_returning_null](https://dart.dev/tools/linter-rules/avoid_returning_null)