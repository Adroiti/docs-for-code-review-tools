Pattern: Unnecessary `final`

Issue: -

## Description

`var` is shorter, and `final` does not change the meaning of the code.

Example of **incorrect** code:
```dart
void badMethod() {
 final label = 'Final or var?';
 for (final char in ['v', 'a', 'r']) {
  print(char);
 }
}
```

Example of **correct** code:
```dart
void goodMethod() {
 var label = 'Final or var?';
 for (var char in ['v', 'a', 'r']) {
  print(char);
 }
}
```

## Further Reading

* [Linter for Dart - unnecessary_final](https://dart-lang.github.io/linter/lints/unnecessary_final.html)