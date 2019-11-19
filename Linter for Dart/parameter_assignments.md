Pattern: Reassigning parameter

Issue: -

## Description

Assigning new values to parameters is generally a bad practice unless an
operator such as `??=` is used. Otherwise, arbitrarily reassigning parameters
is usually a mistake.

Example of **incorrect** code:
```dart
void badFunction(int parameter) { // LINT
 parameter = 4;
}
```

Example of **incorrect** code:
```dart
void badFunction(int required, {int optional: 42}) { // LINT
 optional ??= 8;
}
```

Example of **incorrect** code:
```dart
void badFunctionPositional(int required, [int optional = 42]) { // LINT
 optional ??= 8;
}
```

Example of **incorrect** code:
```dart
class A {
  void badMethod(int parameter) { // LINT
  parameter = 4;
 }
}
```

Example of **correct** code:
```dart
void ok(String parameter) {
 print(parameter);
}
```

Example of **correct** code:
```dart
void actuallyGood(int required, {int optional}) { // OK
 optional ??= ...;
}
```

Example of **correct** code:
```dart
void actuallyGoodPositional(int required, [int optional]) { // OK
 optional ??= ...;
}
```

Example of **correct** code:
```dart
class A {
 void ok(String parameter) {
  print(parameter);
 }
}
```

## Further Reading

* [Linter for Dart - parameter_assignments](https://dart-lang.github.io/linter/lints/parameter_assignments.html)