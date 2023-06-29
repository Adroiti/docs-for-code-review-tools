Pattern: Missing use of function type syntax for parameter

Issue: -

## Description

Use generic function type syntax for parameters.

Example of **incorrect** code:
```dart
Iterable<T> where(bool predicate(T element)) {}
```

Example of **correct** code:
```dart
Iterable<T> where(bool Function(T) predicate) {}
```

## Further Reading

* [Linter for Dart - use_function_type_syntax_for_parameters](https://dart.dev/tools/linter-rules/use_function_type_syntax_for_parameters)