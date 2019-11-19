Pattern: Use of type as parameter name

Issue: -

## Description

**AVOID** using a parameter name that is the same as an existing type.

Example of **incorrect** code:
```dart
m(f(int));
```

Example of **correct** code:
```dart
m(f(int v));
```

## Further Reading

* [Linter for Dart - avoid_types_as_parameter_names](https://dart-lang.github.io/linter/lints/avoid_types_as_parameter_names.html)