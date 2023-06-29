Pattern: Missing use of int literal

Issue: -

## Description

**DO** use int literals rather than the corresponding double literal.

Example of **incorrect** code:
```dart
const double myDouble = 8.0;
final anotherDouble = myDouble + 7.0e2;
main() {
 someMethod(6.0);
}
```

Example of **correct** code:
```dart
const double myDouble = 8;
final anotherDouble = myDouble + 700;
main() {
 someMethod(6);
}
```

## Further Reading

* [Linter for Dart - prefer_int_literals](https://dart.dev/tools/linter-rules/prefer_int_literals)