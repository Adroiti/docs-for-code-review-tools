Pattern: Use of field initializer in `const` class

Issue: -

## Description

Instead of `final x = const expr;`, you should write `get x => const expr;` and
not allocate a useless field. As of April 2018 this is true for the VM, but not
for code that will be compiled to JS.

Example of **incorrect** code:
```dart
class A {
 final a = const [];
 const A();
}
```

Example of **correct** code:
```dart
class A {
 get a => const [];
 const A();
}
```

## Further Reading

* [Linter for Dart - avoid_field_initializers_in_const_classes](https://dart.dev/tools/linter-rules/avoid_field_initializers_in_const_classes)