Pattern: Missing annotation for redeclared member

Issue: -

## Description

**DO** annotate redeclared members.

This practice improves code readability and helps protect against
unintentionally redeclaring members or being surprised when a member ceases to
redeclare (due for example to a rename refactoring).

Example of **incorrect** code:

```dart
class C {
 void f() { }
}

extension type E(C c) implements C {
 void f() {
  ...
 }
}
```

Example of **correct** code:

```dart
import 'package:meta/meta.dart';

class C {
 void f() { }
}

extension type E(C c) implements C {
 @redeclare
 void f() {
  ...
 }
}
```

## Further Reading

* [Linter for Dart - annotate_redeclares](https://dart.dev/tools/linter-rules/annotate_redeclares)