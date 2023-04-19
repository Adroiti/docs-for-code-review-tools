Pattern: Use of type literal in constant pattern

Issue: -

## Description

Use `== TypeName` or `TypeName _` instead of type literals in patterns.

Example of **incorrect** code:
```dart
void f(Type x) {
 if (x case int) {
  print('int');
 }
}
```

Example of **correct** code:
```dart
void f(Type x) {
 if (x case == int) {
  print('int');
 }
}
```

## Further Reading

* [Linter for Dart - type_literal_in_constant_pattern](https://dart-lang.github.io/linter/lints/type_literal_in_constant_pattern.html)