Pattern: Use of `default` clause

Issue: -

## Description

Switches on enums and enum-like classes should not use a `default` clause.

Enum-like classes are defined as concrete (non-abstract) classes that have:
 * only private non-factory constructors
 * two or more static const fields whose type is the enclosing class and
 * no subclasses of the class in the defining library

**DO** define default behavior outside switch statements.

Example of **correct** code:

```dart
 switch (testEnum) {
  case TestEnum.A:
   return '123';
  case TestEnum.B:
   return 'abc';
 }
 // Default here.
 return null;
```

Example of **incorrect** code:

```dart
 switch (testEnum) {
  case TestEnum.A:
   return '123';
  case TestEnum.B:
   return 'abc';
  default:
   return null;
 }
```

## Further Reading

* [Linter for Dart - no_default_cases](https://dart.dev/tools/linter-rules/no_default_cases)