Pattern: Missing use of matching super parameters

Issue: -

## Description

**DO** use super parameter names that match their corresponding super constructor's parameter names.

Example of **incorrect** code:

```dart
class Rectangle {
 final int width;
 final int height;
 
 Rectangle(this.width, this.height);
}

class ColoredRectangle extends Rectangle {
 final Color color;
 
 ColoredRectangle(
  this.color,
  super.height, // Bad, actually corresponds to the `width` parameter.
  super.width, // Bad, actually corresponds to the `height` parameter.
 ); 
}
```

Example of **correct** code:

```dart
class Rectangle {
 final int width;
 final int height;
 
 Rectangle(this.width, this.height);
}

class ColoredRectangle extends Rectangle {
 final Color color;
 
 ColoredRectangle(
  this.color,
  super.width,
  super.height, 
 ); 
}
```

## Further Reading

* [Linter for Dart - matching_super_parameters](https://dart-lang.github.io/linter/lints/matching_super_parameters.html)