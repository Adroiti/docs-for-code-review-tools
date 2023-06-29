Pattern: Missing use of `final` in for-each loop variable

Issue: -

## Description

Declaring for-each loop variables as `final` when possible is a good practice
because it helps avoid accidental reassignments and allows the compiler to do
optimizations.

Example of **incorrect** code:
```dart
for (var element in elements) { // LINT
 print('Element: $element');
}
```

Example of **correct** code:
```dart
for (final element in elements) {
 print('Element: $element');
}
```

Example of **correct** code:
```dart
for (var element in elements) {
 element = element + element;
 print('Element: $element');
}
```

## Further Reading

* [Linter for Dart - prefer_final_in_for_each](https://dart.dev/tools/linter-rules/prefer_final_in_for_each)