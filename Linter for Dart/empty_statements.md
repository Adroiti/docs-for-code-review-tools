Pattern: Empty statement

Issue: -

## Description

Empty statements almost always indicate a bug.

For example,

Example of **incorrect** code:
```dart
if (complicated.expression.foo());
 bar();
```

Formatted with `dartfmt` the bug becomes obvious:

```
if (complicated.expression.foo()) ;
bar();

```

Better to avoid the empty statement altogether.

Example of **correct** code:
```dart
if (complicated.expression.foo())
 bar();
```

## Further Reading

* [Linter for Dart - empty_statements](https://dart.dev/tools/linter-rules/empty_statements)