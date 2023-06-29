Pattern: Missing use of `const` to create immutable

Issue: -

## Description

**PREFER** using `const` for instantiating list, map and set literals used as parameters in immutable class instantiations.

Example of **incorrect** code:
```dart
@immutable
class A {
 A(this.v);
 final v;
}

A a1 = new A([1]);
A a2 = new A({});
```

Example of **correct** code:
```dart
A a1 = new A(const [1]);
A a2 = new A(const {});
```

## Further Reading

* [Linter for Dart - prefer_const_literals_to_create_immutables](https://dart.dev/tools/linter-rules/prefer_const_literals_to_create_immutables)