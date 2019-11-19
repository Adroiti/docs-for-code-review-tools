Pattern: Missing use of `to___()`/`as___()` for method name

Issue: -

## Description

**PREFER** naming a method `to___()` if it copies the object's state to a new object.

**PREFER** naming a method `as___()` if it returns a different representation backed by the original object.

Example of **incorrect** code:
```dart
class Bar {
 Foo myMethod() {
  return Foo.from(this);
 }
}
```

Example of **correct** code:
```dart
class Bar {
 Foo toFoo() {
  return Foo.from(this);
 }
}
```

Example of **correct** code:
```dart
class Bar {
 Foo asFoo() {
  return Foo.from(this);
 }
}
```

## Further Reading

* [Linter for Dart - use_to_and_as_if_applicable](https://dart-lang.github.io/linter/lints/use_to_and_as_if_applicable.html)