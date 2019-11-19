Pattern: Use of single cascade in expression statement

Issue: -

## Description

**AVOID** single cascade in expression statements.

Example of **incorrect** code:
```dart
o..m();
```

Example of **correct** code:
```dart
o.m();
```

## Further Reading

* [Linter for Dart - avoid_single_cascade_in_expression_statements](https://dart-lang.github.io/linter/lints/avoid_single_cascade_in_expression_statements.html)