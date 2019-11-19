Pattern: Use of empty `catch`

Issue: -

## Description

In general, empty catch blocks should be avoided. In cases where they are
intended, a comment should be provided to explain why exceptions are being
caught and suppressed. Alternatively, the exception identifier can be named with
underscores (e.g., `_`) to indicate that we intend to skip it.

Example of **incorrect** code:
```dart
try {
 ...
} catch(exception) { }
```

Example of **correct** code:
```dart
try {
 ...
} catch(e) {
 // ignored, really.
}

// Alternatively:
try {
 ...
} catch(_) { }

// Better still:
try {
 ...
} catch(e) {
 doSomething(e);
}
```

## Further Reading

* [Linter for Dart - empty_catches](https://dart-lang.github.io/linter/lints/empty_catches.html)