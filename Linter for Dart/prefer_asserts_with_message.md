Pattern: Missing use of `assert` with message

Issue: -

## Description

When assertions fail it's not always simple to understand why. Adding a message
to the `assert` helps the developer to understand why the `AssertionError` occurs.

Example of **incorrect** code:
```dart
f(a) {
 assert(a != null);
}

class A {
 A(a) : assert(a != null);
}
```

Example of **correct** code:
```dart
f(a) {
 assert(a != null, 'a must not be null');
}

class A {
 A(a) : assert(a != null, 'a must not be null');
}
```

## Further Reading

* [Linter for Dart - prefer_asserts_with_message](https://dart.dev/tools/linter-rules/prefer_asserts_with_message)