Pattern: Returning `this` from a method

Issue: -

## Description

Returning `this` from a method is redundant; Dart has a cascade operator which
allows method chaining universally.

Returning `this` is allowed for:

- operators
- methods with a return type different of the current class
- methods defined in parent classes / mixins or interfaces
- methods defined in extensions

Example of **incorrect** code:
```dart
var buffer = StringBuffer()
 .write('one')
 .write('two')
 .write('three');
```

Example of **correct** code:
```dart
var buffer = StringBuffer()
 ..write('one')
 ..write('two')
 ..write('three');
```

## Further Reading

* [Linter for Dart - avoid_returning_this](https://dart.dev/tools/linter-rules/avoid_returning_this)