Pattern: Use of `{}` for empty constructor body

Issue: -

## Description

In Dart, a constructor with an empty body can be terminated with just a
semicolon. This is required for const constructors. For consistency and
brevity, other constructors should also do this.

Example of **correct** code:
```dart
class Point {
 int x, y;
 Point(this.x, this.y);
}
```

Example of **incorrect** code:
```dart
class Point {
 int x, y;
 Point(this.x, this.y) {}
}
```

## Further Reading

* [Linter for Dart - empty_constructor_bodies](https://dart.dev/tools/linter-rules/empty_constructor_bodies)
* [Effective Dart](https://dart.dev/guides/language/effective-dart/style)