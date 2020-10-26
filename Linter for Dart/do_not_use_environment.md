Pattern: Use of environment constructor

Issue: -

## Description

Using values derived from the environment at compile-time, creates
hidden global state and makes applications hard to understand and maintain.

Example of **incorrect** code:

```dart
const loggingLevel =
 bool.hasEnvironment('logging') ? String.fromEnvironment('logging') : null;
```

## Further Reading

* [Linter for Dart - do_not_use_environment](https://dart-lang.github.io/linter/lints/do_not_use_environment.html)