Pattern: Use of recursive getter

Issue: -

## Description

Recursive getters are getters which return themselves as a value. This is usually a typo.

Example of **incorrect** code:
```dart
int get field => field; // LINT
```

Example of **incorrect** code:
```dart
int get otherField {
 return otherField; // LINT
}
```

Example of **correct** code:
```dart
int get field => _field;
```

## Further Reading

* [Linter for Dart - recursive_getters](https://dart.dev/tools/linter-rules/recursive_getters)