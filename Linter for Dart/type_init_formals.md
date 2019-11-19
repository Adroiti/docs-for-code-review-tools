Pattern: Use of type annotate for initializing formal

Issue: -

## Description

If a constructor parameter is using `this.x` to initialize a field, then the
type of the parameter is understood to be the same type as the field.

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
 Point(int this.x, int this.y);
}
```

## Further Reading

* [Linter for Dart - type_init_formals](https://dart-lang.github.io/linter/lints/type_init_formals.html)