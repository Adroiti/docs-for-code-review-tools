Pattern: Wrong combinator order

Issue: -

## Description

**DO** sort combinator names alphabetically.

Example of **incorrect** code:

```dart
import 'a.dart' show B, A hide D, C;
export 'a.dart' show B, A hide D, C;
```

Example of **correct** code:

```dart
import 'a.dart' show A, B hide C, D;
export 'a.dart' show A, B hide C, D;
```

## Further Reading

* [Linter for Dart - combinators_ordering](https://dart.dev/tools/linter-rules/combinators_ordering)