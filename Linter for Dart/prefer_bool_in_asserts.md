Pattern: Missing use of boolean in `assert`

Issue: -

## Description

Not using booleans in assert conditions can lead to code where it isn't clear
what the intention of the assert statement is.

Example of **incorrect** code:
```dart
assert(() {
 f();
 return true;
});
```

Example of **correct** code:
```dart
assert(() {
 f();
 return true;
}());
```

**DEPRECATED:** In Dart 2, `assert`s no longer accept non-`bool` values so this
rule is made redundant by the Dart analyzer's basic checks and is no longer
necessary.
 
The rule will be removed in a future Linter release.

## Further Reading

* [Linter for Dart - prefer_bool_in_asserts](https://dart-lang.github.io/linter/lints/prefer_bool_in_asserts.html)