Pattern: Unseparated control expression from its statement

Issue: -

## Description

Don't put the statement part of an `if`, `for`, `while`, `do` on the same line
as the expression, even if it is short. Doing so makes it unclear that there
is relevant code there. This is especially important for early returns.

Example of **correct** code:
```dart
if (notReady)
 return;

if (notReady)
 return;
else
 print('ok')

while (condition)
 i += 1;
```

Example of **incorrect** code:
```dart
if (notReady) return;

if (notReady)
 return;
else print('ok')

while (condition) i += 1;
```

## Further Reading

* [Linter for Dart - always_put_control_body_on_new_line](https://dart.dev/tools/linter-rules/always_put_control_body_on_new_line)
* [Flutter style guide](https://flutter.dev/style-guide/)