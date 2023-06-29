Pattern: Use of return type on setter

Issue: -

## Description

As setters do not return a value, declaring the return type of one is redundant.

Example of **correct** code:
```dart
set speed(int ms);
```

Example of **incorrect** code:
```dart
void set speed(int ms);
```

## Further Reading

* [Linter for Dart - avoid_return_types_on_setters](https://dart.dev/tools/linter-rules/avoid_return_types_on_setters)