Pattern: Missing use of `rethrow`

Issue: -

## Description

As Dart provides `rethrow` as a feature, it should be used to improve terseness and readability.

Example of **incorrect** code:
```dart
try {
 somethingRisky();
} catch(e) {
 if (!canHandle(e)) throw e;
 handle(e);
}
```

Example of **correct** code:
```dart
try {
 somethingRisky();
} catch(e) {
 if (!canHandle(e)) rethrow;
 handle(e);
}
```

## Further Reading

* [Linter for Dart - use_rethrow_when_possible](https://dart-lang.github.io/linter/lints/use_rethrow_when_possible.html)