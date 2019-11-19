Pattern: Literal-only boolean expression

Issue: -

## Description

Conditional statements using a condition which cannot be anything but FALSE have
the effect of making blocks of code non-functional. If the condition cannot
evaluate to anything but `true`, the conditional statement is completely
redundant, and makes the code less readable.

It is quite likely that the code does not match the programmer's intent.
Either the condition should be removed or it should be updated so that it does
not always evaluate to `true` or `false`.

Example of **incorrect** code:
```dart
void bad() {
 if (true) {} // LINT
}
```

Example of **incorrect** code:
```dart
void bad() {
 if (true && 1 != 0) {} // LINT
}
```

Example of **incorrect** code:
```dart
void bad() {
 if (1 != 0 && true) {} // LINT
}
```

Example of **incorrect** code:
```dart
void bad() {
 if (1 < 0 && true) {} // LINT
}
```

Example of **incorrect** code:
```dart
void bad() {
 if (true && false) {} // LINT
}
```

Example of **incorrect** code:
```dart
void bad() {
 if (1 != 0) {} // LINT
}
```

Example of **incorrect** code:
```dart
void bad() {
 if (true && 1 != 0 || 3 < 4) {} // LINT
}
```

Example of **incorrect** code:
```dart
void bad() {
 if (1 != 0 || 3 < 4 && true) {} // LINT
}
```

## Further Reading

* [Linter for Dart - literal_only_boolean_expressions](https://dart-lang.github.io/linter/lints/literal_only_boolean_expressions.html)