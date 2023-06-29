Pattern: Missing deprecation message

Issue: -

## Description

**DO** specify a deprecation message (with migration instructions and/or a removal schedule) in the Deprecation constructor.

Example of **incorrect** code:
```dart
@deprecated
void oldFunction(arg1, arg2) {}
```

Example of **correct** code:
```dart
@Deprecated("""
[oldFunction] is being deprecated in favor of [newFunction] (with slightly
different parameters; see [newFunction] for more information). [oldFunction]
will be removed on or after the 4.0.0 release.
""")
void oldFunction(arg1, arg2) {}
```

## Further Reading

* [Linter for Dart - provide_deprecation_message](https://dart.dev/tools/linter-rules/provide_deprecation_message)