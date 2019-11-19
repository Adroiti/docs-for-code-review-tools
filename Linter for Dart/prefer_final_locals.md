Pattern: Missing use of `final` for variable

Issue: -

## Description

Declaring variables as final when possible is a good practice because it helps
avoid accidental reassignments and allows the compiler to do optimizations.

Example of **incorrect** code:
```dart
void badMethod() {
 var label = 'hola mundo! badMethod'; // LINT
 print(label);
}
```

Example of **correct** code:
```dart
void goodMethod() {
 final label = 'hola mundo! goodMethod';
 print(label);
}
```

Example of **correct** code:
```dart
void mutableCase() {
 var label = 'hola mundo! mutableCase';
 print(label);
 label = 'hello world';
 print(label);
}
```

## Further Reading

* [Linter for Dart - prefer_final_locals](https://dart-lang.github.io/linter/lints/prefer_final_locals.html)