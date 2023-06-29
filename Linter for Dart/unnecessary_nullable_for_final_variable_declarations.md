Pattern: Unnecessary nullable for final variable

Issue: -

## Description

Use a non-nullable type for a final variable initialized with a non-nullable value.

Example of **incorrect** code:

```dart
final int? i = 1;
```

Example of **correct** code:

```dart
final int i = 1;
```

## Further Reading

* [Linter for Dart - unnecessary_nullable_for_final_variable_declarations](https://dart.dev/tools/linter-rules/unnecessary_nullable_for_final_variable_declarations)