Pattern: Missing use of final parameter

Issue: -

## Description

**DO** prefer declaring parameters as final if they are not reassigned in
the function body.

Declaring parameters as final when possible is a good practice because it helps
avoid accidental reassignments.

Example of **incorrect** code:

```dart
void badParameter(String label) { // LINT
 print(label);
}
```

Example of **correct** code:
```dart
void goodParameter(final String label) { // OK
 print(label);
}
```

Example of **incorrect** code:
```dart
void badExpression(int value) => print(value); // LINT
```

Example of **correct** code:

```dart
void goodExpression(final int value) => print(value); // OK
```

Example of **incorrect** code:

```dart
[1, 4, 6, 8].forEach((value) => print(value + 2)); // LINT
```

Example of **correct** code:

```dart
[1, 4, 6, 8].forEach((final value) => print(value + 2)); // OK
```

Example of **correct** code:

```dart
void mutableParameter(String label) { // OK
 print(label);
 label = 'Hello Linter!';
 print(label);
}
```

## Further Reading

* [Linter for Dart - prefer_final_parameters](https://dart-lang.github.io/linter/lints/prefer_final_parameters.html)