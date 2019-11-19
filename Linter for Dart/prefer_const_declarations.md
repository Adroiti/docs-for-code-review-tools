Pattern: Missing use of `const`

Issue: -

## Description

Const declarations are more hot-reload friendly and allow to use const
constructors if an instantiation references this declaration.

Example of **correct** code:
```dart
const o = const [];

class A {
 static const o = const [];
}
```

Example of **incorrect** code:
```dart
final o = const [];

class A {
 static final o = const [];
}
```

## Further Reading

* [Linter for Dart - prefer_const_declarations](https://dart-lang.github.io/linter/lints/prefer_const_declarations.html)