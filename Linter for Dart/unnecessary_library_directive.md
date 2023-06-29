Pattern: Unnecessary library directive

Issue: -

## Description

**DO** use library directives if you want to document a library and/or annotate 
a library.

Example of **incorrect** code:

```dart
library;
```

Example of **correct** code:

```dart
/// This library does important things
library;
```

```dart
@TestOn('js')
library;
```

NOTE: Due to limitations with this lint, libraries with parts will not be
flagged for unnecessary library directives.

## Further Reading

* [Linter for Dart - unnecessary_library_directive](https://dart.dev/tools/linter-rules/unnecessary_library_directive)