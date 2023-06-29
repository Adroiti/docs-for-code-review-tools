Pattern: Use of bool literal in conditional expression

Issue: -

## Description

**AVOID** bool literals in conditional expressions.

Example of **incorrect** code:
```dart
condition ? true : boolExpression
condition ? false : boolExpression
condition ? boolExpression : true
condition ? boolExpression : false
```

Example of **correct** code:
```dart
condition || boolExpression
!condition && boolExpression
!condition || boolExpression
condition && boolExpression
```

## Further Reading

* [Linter for Dart - avoid_bool_literals_in_conditional_expressions](https://dart.dev/tools/linter-rules/avoid_bool_literals_in_conditional_expressions)