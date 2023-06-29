Pattern: Importing implementation file from another package

Issue: -

## Description

The libraries inside `lib` are publicly visible: other packages are free to
import them. But much of a package's code is internal implementation libraries
that should only be imported and used by the package itself. Those go inside a
subdirectory of `lib` called `src`. You can create subdirectories in there if
it helps you organize things.

You are free to import libraries that live in `lib/src` from within other Dart
code in the same package (like other libraries in `lib`, scripts in `bin`,
and tests) but you should never import from another package's `lib/src`
directory. Those files are not part of the package's public API, and they
might change in ways that could break your code.

Example of **incorrect** code:
```dart
// In 'road_runner'
import 'package:acme/lib/src/internals.dart;
```

## Further Reading

* [Linter for Dart - implementation_imports](https://dart.dev/tools/linter-rules/implementation_imports)