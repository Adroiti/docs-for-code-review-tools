Pattern: Use of multiple declarations per line

Issue: -

## Description

**DON'T** declare multiple variables on a single line.

Example of **incorrect** code:

```dart
String? foo, bar, baz;
```

Example of **correct** code:

```dart
String? foo;
String? bar;
String? baz;
```

## Further Reading

* [Linter for Dart - avoid_multiple_declarations_per_line](https://dart-lang.github.io/linter/lints/avoid_multiple_declarations_per_line.html)