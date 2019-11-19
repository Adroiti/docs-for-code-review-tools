Pattern: Missing doc for public API

Issue: -

## Description

Public APIs consist in everything in your package's `lib` folder, minus
implementation files in `lib/src`, adding elements explicitly exported with an
`export` directive.

For example, given `lib/foo.dart`:
```
export 'src/bar.dart' show Bar;
export 'src/baz.dart';

class Foo { }

class _Foo { }
```
its API includes:

* `Foo` (but not `_Foo`)
* `Bar` (exported) and
* all *public* elements in `src/baz.dart`

All public API members should be documented with `///` doc-style comments.

Example of **correct** code:
```dart
/// A Foo.
abstract class Foo {
 /// Start foo-ing.
 void start() => _start();

 _start();
}
```

Example of **incorrect** code:
```dart
class Bar {
 void bar();
}
```

Advice for writing good doc comments can be found in the
[Doc Writing Guidelines](https://www.dartlang.org/guides/language/effective-dart/documentation).

## Further Reading

* [Linter for Dart - package_api_docs](https://dart-lang.github.io/linter/lints/package_api_docs.html)