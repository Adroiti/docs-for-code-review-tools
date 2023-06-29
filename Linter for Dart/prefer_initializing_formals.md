Pattern: Missing use of initializing formal

Issue: -

## Description

Using initializing formals when possible makes your code more terse.

Example of **incorrect** code:
```dart
class Point {
 num x, y;
 Point(num x, num y) {
  this.x = x;
  this.y = y;
 }
}
```

Example of **correct** code:
```dart
class Point {
 num x, y;
 Point(this.x, this.y);
}
```

Example of **incorrect** code:
```dart
class Point {
 num x, y;
 Point({num x, num y}) {
  this.x = x;
  this.y = y;
 }
}
```

Example of **correct** code:
```dart
class Point {
 num x, y;
 Point({this.x, this.y});
}
```

**NOTE**
This rule will not generate a lint for named parameters unless the parameter
name and the field name are the same. The reason for this is that resolving
such a lint would require either renaming the field or renaming the parameter,
and both of those actions would potentially be a breaking change. For example,
the following will not generate a lint:

```
class Point {
 bool isEnabled;
 Point({bool enabled}) {
  this.isEnabled = enable; // OK
 }
}
```

## Further Reading

* [Linter for Dart - prefer_initializing_formals](https://dart.dev/tools/linter-rules/prefer_initializing_formals)