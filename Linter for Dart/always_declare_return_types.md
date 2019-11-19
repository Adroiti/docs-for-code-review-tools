Pattern: Missing method return type

Issue: -

## Description

When declaring a method or function *always* specify a return type.
Declaring return types for functions helps improve your codebase by allowing the
analyzer to more adequately check your code for errors that could occur during
runtime.

Example of **incorrect** code:
```dart
main() { }

_bar() => _Foo();

class _Foo {
 _foo() => 42;
}
```

Example of **correct** code:
```dart
void main() { }

_Foo _bar() => _Foo();

class _Foo {
 int _foo() => 42;
}

typedef bool predicate(Object o);
```

## Further Reading

* [Linter for Dart - always_declare_return_types](https://dart-lang.github.io/linter/lints/always_declare_return_types.html)