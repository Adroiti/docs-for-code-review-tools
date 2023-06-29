Pattern: Renaming overridden method parameter

Issue: -

## Description

Methods that override another method, but do not have their own documentation
comment, will inherit the overridden method's comment when dartdoc produces
documentation. If the inherited method contains the name of the parameter (in
square brackets), then dartdoc cannot link it correctly.

Example of **incorrect** code:
```dart
abstract class A {
 m(a);
}

abstract class B extends A {
 m(b);
}
```

Example of **correct** code:
```dart
abstract class A {
 m(a);
}

abstract class B extends A {
 m(a);
}
```

## Further Reading

* [Linter for Dart - avoid_renaming_method_parameters](https://dart.dev/tools/linter-rules/avoid_renaming_method_parameters)