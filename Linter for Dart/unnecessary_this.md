Pattern: Unnecessary `this`

Issue: -

## Description

**DON'T** use `this` when not needed to avoid shadowing.

Example of **incorrect** code:
```dart
class Box {
 var value;
 void update(new_value) {
  this.value = new_value;
 }
}
```

Example of **correct** code:
```dart
class Box {
 var value;
 void update(new_value) {
  value = new_value;
 }
}
```

Example of **correct** code:
```dart
class Box {
 var value;
 void update(value) {
  this.value = value;
 }
}
```

## Further Reading

* [Linter for Dart - unnecessary_this](https://dart-lang.github.io/linter/lints/unnecessary_this.html)