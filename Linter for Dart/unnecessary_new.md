Pattern: Unnecessary `new`

Issue: -

## Description

**AVOID** `new` keyword to create instances.

Example of **incorrect** code:
```dart
class A { A(); }
m(){
 final a = new A();
}
```

Example of **correct** code:
```dart
class A { A(); }
m(){
 final a = A();
}
```

## Further Reading

* [Linter for Dart - unnecessary_new](https://dart-lang.github.io/linter/lints/unnecessary_new.html)