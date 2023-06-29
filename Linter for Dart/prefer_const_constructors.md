Pattern: Missing use of `const` constructor

Issue: -

## Description

If a `const` constructor is available, it is preferable to use it.

Example of **correct** code:
```dart
class A {
 const A();
}

void accessA() {
 A a = const A();
}
```

Example of **correct** code:
```dart
class A {
 final int x;

 const A(this.x);
}

A foo(int x) => new A(x);
```

Example of **incorrect** code:
```dart
class A {
 const A();
}

void accessA() {
 A a = new A();
}
```

## Further Reading

* [Linter for Dart - prefer_const_constructors](https://dart.dev/tools/linter-rules/prefer_const_constructors)