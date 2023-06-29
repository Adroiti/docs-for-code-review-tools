Pattern: Use of empty `else`

Issue: -

## Description

**AVOID** empty else statements.

Example of **incorrect** code:
```dart
if (x > y)
 print("1");
else ;
 print("2");
```

## Further Reading

* [Linter for Dart - avoid_empty_else](https://dart.dev/tools/linter-rules/avoid_empty_else)