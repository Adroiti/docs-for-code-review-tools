Pattern: Use of private `typedef` function

Issue: -

## Description

**AVOID** private `typedef` functions used only once. Prefer inline function syntax.

Example of **incorrect** code:
```dart
typedef void _F();
m(_F f);
```

Example of **correct** code:
```dart
m(void Function() f);
```

## Further Reading

* [Linter for Dart - avoid_private_typedef_functions](https://dart.dev/tools/linter-rules/avoid_private_typedef_functions)