Pattern: Missing use of string in part of directive

Issue: -

## Description

From [effective dart](https://dart.dev/guides/language/effective-dart/usage#do-use-strings-in-part-of-directives):

**DO** use strings in `part of` directives.

Example of **incorrect** code:

```dart
part of my_library;
```

Example of **correct** code:

```dart
part of '../../my_library.dart';
```

## Further Reading

* [Linter for Dart - use_string_in_part_of_directives](https://dart-lang.github.io/linter/lints/use_string_in_part_of_directives.html)