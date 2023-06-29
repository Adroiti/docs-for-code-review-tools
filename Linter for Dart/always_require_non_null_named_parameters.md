Pattern: Missing `@required` for non-null named parameter

Issue: -

## Description

**DO** specify `@required` on named parameters without a default value on which 
an `assert(param != null)` is done.

Example of **correct** code:
```dart
m1({@required a}) {
 assert(a != null);
}

m2({a: 1}) {
 assert(a != null);
}
```

Example of **incorrect** code:
```dart
m1({a}) {
 assert(a != null);
}
```

NOTE: Only asserts at the start of the bodies will be taken into account.

## Further Reading

* [Linter for Dart - always_require_non_null_named_parameters](https://dart.dev/tools/linter-rules/always_require_non_null_named_parameters)