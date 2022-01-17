Pattern: Use of file in conditional import

Issue: -

## Description

**DON'T** reference files that do not exist in conditional imports.

Code may fail at runtime if the condition evaluates such that the missing file needs to be imported.

Example of **incorrect** code:
```dart
import 'file_that_does_exist.dart'
 if (condition) 'file_that_does_not_exist.dart';
```

Example of **correct** code:
```dart
import 'file_that_does_exist.dart'
 if (condition) 'file_that_also_does_exist.dart';
```

## Further Reading

* [Linter for Dart - conditional_uri_does_not_exist](https://dart-lang.github.io/linter/lints/conditional_uri_does_not_exist.html)