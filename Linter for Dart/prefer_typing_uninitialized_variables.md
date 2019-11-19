Pattern: Missing type annotation for uninitialized variable/field

Issue: -

## Description

Forgoing type annotations for uninitialized variables is a bad practice because
you may accidentally assign them to a type that you didn't originally intend to.

Example of **incorrect** code:
```dart
class BadClass {
 static var bar; // LINT
 var foo; // LINT

 void method() {
  var bar; // LINT
  bar = 5;
  print(bar);
 }
}
```

Example of **incorrect** code:
```dart
void aFunction() {
 var bar; // LINT
 bar = 5;
 ...
}
```

Example of **correct** code:
```dart
class GoodClass {
 static var bar = 7;
 var foo = 42;
 int baz; // OK

 void method() {
  int baz;
  var bar = 5;
  ...
 }
}
```

## Further Reading

* [Linter for Dart - prefer_typing_uninitialized_variables](https://dart-lang.github.io/linter/lints/prefer_typing_uninitialized_variables.html)