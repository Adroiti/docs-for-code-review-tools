Pattern: Throwing instance that does not extend `Error`/`Exception`

Issue: -

## Description

**DO** throw only instances of classes that extend `dart.core.Error` or
`dart.core.Exception`.

Throwing instances that do not extend `Error` or `Exception` is a bad practice;
doing this is usually a hack for something that should be implemented more
thoroughly.

Example of **incorrect** code:
```dart
void throwString() {
 throw 'hello world!'; // LINT
}
```

Example of **correct** code:
```dart
void throwArgumentError() {
 Error error = new ArgumentError('oh!');
 throw error; // OK
}
```

## Further Reading

* [Linter for Dart - only_throw_errors](https://dart.dev/tools/linter-rules/only_throw_errors)