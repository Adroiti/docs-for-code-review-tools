Pattern: Use of no-op primitive operation

Issue: -

## Description

Some operations on primitive types are idempotent and can be removed.

Example of **incorrect** code:

```dart
doubleValue.toDouble();

intValue.toInt();
intValue.round();
intValue.ceil();
intValue.floor();
intValue.truncate();

string.toString();
string = 'hello\n'
  'world\n'
  ''; // useless empty string
```

## Further Reading

* [Linter for Dart - noop_primitive_operations](https://dart.dev/tools/linter-rules/noop_primitive_operations)