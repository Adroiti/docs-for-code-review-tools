Pattern: Use of explicit `Error` catch

Issue: -

## Description

Errors differ from Exceptions in that Errors can be analyzed and prevented prior
to runtime. It should almost never be necessary to catch an error at runtime.

Example of **incorrect** code:
```dart
try {
 somethingRisky();
} on Error catch(e) {
 doSomething(e);
}
```

Example of **correct** code:
```dart
try {
 somethingRisky();
} on Exception catch(e) {
 doSomething(e);
}
```

## Further Reading

* [Linter for Dart - avoid_catching_errors](https://dart.dev/tools/linter-rules/avoid_catching_errors)