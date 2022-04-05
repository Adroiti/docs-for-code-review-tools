Pattern: Missing use of super-initializer parameter

Issue: -

## Description

"Forwarding constructor"s, that do nothing except forward parameters to their 
superclass constructors should take advantage of super-initializer parameters 
rather than repeating the names of parameters when passing them to the 
superclass constructors. This makes the code more concise and easier to read
and maintain.

**DO** use super-initializer parameters where possible.

Example of **incorrect** code:
```dart
class A {
 A({int? x, int? y});
}
class B extends A {
 B({int? x, int? y}) : super(x: x, y: y);
}
```

Example of **correct** code:
```dart
class A {
 A({int? x, int? y});
}
class B extends A {
 B({super.x, super.y});
}
```

## Further Reading

* [Linter for Dart - use_super_parameters](https://dart-lang.github.io/linter/lints/use_super_parameters.html)