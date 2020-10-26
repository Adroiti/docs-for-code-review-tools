Pattern: Missing use of late for private member

Issue: -

## Description

Use late for private members with non-nullable types that are always expected to
be non-null. Thus it's clear that the field is not expected to be `null` and it
avoids null checks.

Example of **incorrect** code:

```dart
int? _i;
m() {
 _i!.abs();
}
```

Example of **correct** code:

```dart
late int _i;
m() {
 _i.abs();
}
```

## Further Reading

* [Linter for Dart - use_late_for_private_fields_and_variables](https://dart-lang.github.io/linter/lints/use_late_for_private_fields_and_variables.html)