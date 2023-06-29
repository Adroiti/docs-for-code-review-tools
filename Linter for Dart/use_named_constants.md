Pattern: Missing use of named constant

Issue: -

## Description

Where possible, use already defined const values.

Example of **incorrect** code:

```dart
const Duration(seconds: 0);
```

Example of **correct** code:

```dart
Duration.zero;
```

## Further Reading

* [Linter for Dart - use_named_constants](https://dart.dev/tools/linter-rules/use_named_constants)