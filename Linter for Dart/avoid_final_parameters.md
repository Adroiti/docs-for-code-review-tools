Pattern: Use of `final` parameter

Issue: -

## Description

**AVOID** declaring parameters as final.

Declaring parameters as final can lead to unecessarily verbose code, especially when using the "parameter_assignments" rule.

Example of **correct** code:

```dart
void badParameter(String label) { // OK
 print(label);
}
```

Example of **incorrect** code:
```dart
void goodParameter(final String label) { // LINT
 print(label);
}
```

Example of **correct** code:
```dart
void badExpression(int value) => print(value); // OK
```

Example of **incorrect** code:
```dart
void goodExpression(final int value) => print(value); // LINT
```

Example of **correct** code:
```dart
[1, 4, 6, 8].forEach((value) => print(value + 2)); // OK
```

Example of **incorrect** code:
```dart
[1, 4, 6, 8].forEach((final value) => print(value + 2)); // LINT
```

## Further Reading

* [Linter for Dart - avoid_final_parameters](https://dart-lang.github.io/linter/lints/avoid_final_parameters.html)