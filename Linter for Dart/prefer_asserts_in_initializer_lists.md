Pattern: Missing use of `assert` in initializer list

Issue: -

## Description

**DO** put asserts in initializer list for constructors with only asserts in their body.

Example of **correct** code:
```dart
class A {
 A(int a) : assert(a != null);
}
```

Example of **incorrect** code:
```dart
class A {
 A(int a) {
  assert(a != null);
 }
}
```

## Further Reading

* [Linter for Dart - prefer_asserts_in_initializer_lists](https://dart-lang.github.io/linter/lints/prefer_asserts_in_initializer_lists.html)