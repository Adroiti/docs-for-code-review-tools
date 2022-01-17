Pattern: Use of leading underscore for library prefix

Issue: -

## Description

**DON’T** use a leading underscore for library prefixes.
There is no concept of "private" for library prefixes. When one of those has a
name that starts with an underscore, it sends a confusing signal to the reader. 
To avoid that, don't use leading underscores in those names.

Example of **incorrect** code:

```dart
import 'dart:core' as _core;
```

Example of **correct** code:

```dart
import 'dart:core' as core;
```

## Further Reading

* [Linter for Dart - no_leading_underscores_for_library_prefixes](https://dart-lang.github.io/linter/lints/no_leading_underscores_for_library_prefixes.html)