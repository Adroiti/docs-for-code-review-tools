Pattern: Missing use of constructor over static method

Issue: -

## Description

In most cases, it makes more sense to use a named constructor rather than a static method because it makes instantiation clearer.

Example of **incorrect** code:
```dart
class Point {
 num x, y;
 Point(this.x, this.y);
 static Point polar(num theta, num radius) {
  return new Point(radius * math.cos(theta),
    radius * math.sin(theta));
 }
}
```

Example of **correct** code:
```dart
class Point {
 num x, y;
 Point(this.x, this.y);
 Point.polar(num theta, num radius)
   : x = radius * math.cos(theta),
    y = radius * math.sin(theta);
}
```

## Further Reading

* [Linter for Dart - prefer_constructors_over_static_methods](https://dart-lang.github.io/linter/lints/prefer_constructors_over_static_methods.html)