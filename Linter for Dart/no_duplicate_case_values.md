Pattern: Duplicate `case` value

Issue: -

## Description

This is usually a typo or changed value of constant.

Example of **correct** code:
```dart
const int A = 1;
switch (v) {
 case A:
 case 2:
}
```

Example of **incorrect** code:
```dart
const int A = 1;
switch (v) {
 case 1:
 case 2:
 case A:
 case 2:
}
```

## Further Reading

* [Linter for Dart - no_duplicate_case_values](https://dart-lang.github.io/linter/lints/no_duplicate_case_values.html)