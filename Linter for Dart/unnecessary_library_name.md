Pattern: Unnecessary library name

Issue: -

## Description

**DON'T** have a library name in a library declaration.

Library names are not necessary.

A library does not need a library declaration, but one can be added to attach library documentation and library metadata to. A declaration of `library`; is sufficient for those uses.

The only use of a library name is for a `part` file to refer back to its owning library, but part files should prefer to use a string URI to refer back to the library file, not a library name.

Example of **incorrect** code:

```dart
/// This library has a long name.
library magnificator.src.helper.bananas;
```

Example of **correct** code:

```dart
/// This library is awesome.
library;

part "apart.dart"; // contains: `part of "good_library.dart";`
```

## Further Reading

* [Linter for Dart - unnecessary_library_name](https://dart.dev/tools/linter-rules/unnecessary_library_name)