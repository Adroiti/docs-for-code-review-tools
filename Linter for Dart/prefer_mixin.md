Pattern: Missing use of mixin

Issue: -

## Description

Dart 2.1 introduced a new syntax for mixins that provides a safe way for a mixin
to invoke inherited members using `super`. The new style of mixins should always
be used for types that are to be mixed in. As a result, this lint will flag any
uses of a class in a `with` clause.

Example of **incorrect** code:
```dart
class A {}
class B extends Object with A {}
```

**OK:**
```dart
mixin M {}
class C with M {}
```

## Further Reading

* [Linter for Dart - prefer_mixin](https://dart-lang.github.io/linter/lints/prefer_mixin.html)