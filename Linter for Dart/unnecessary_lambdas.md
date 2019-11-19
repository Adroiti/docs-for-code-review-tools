Pattern: Unnecessary lambda

Issue: -

## Description

**DON'T** create a lambda when a tear-off will do.

Example of **incorrect** code:
```dart
names.forEach((name) {
 print(name);
});
```

Example of **correct** code:
```dart
names.forEach(print);
```

## Further Reading

* [Linter for Dart - unnecessary_lambdas](https://dart-lang.github.io/linter/lints/unnecessary_lambdas.html)