Pattern: Missing use of `const` constructors for immutable

Issue: -

## Description

If a class is immutable, it is usually a good idea to make its constructor a `const` constructor.

Example of **correct** code:
```dart
@immutable
class A {
 final a;
 const A(this.a);
}
```

Example of **incorrect** code:
```dart
@immutable
class A {
 final a;
 A(this.a);
}
```

## Further Reading

* [Linter for Dart - prefer_const_constructors_in_immutables](https://dart-lang.github.io/linter/lints/prefer_const_constructors_in_immutables.html)