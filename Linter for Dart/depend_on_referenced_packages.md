Pattern: Missing dependency on referenced package

Issue: -

## Description

**DO** Depend on referenced packages.

When importing a package, add a dependency on it to your pubspec.

Depending explicitly on packages that you reference ensures they will always
exist and allows you to put a dependency constraint on them to guard you
against breaking changes.

Whether this should be a regular dependency or dev_dependency depends on if it
is referenced from a public file (one under either `lib` or `bin`), or some
other private file.

Example of **incorrect** code:

```dart
import 'package:a/a.dart';
```

```yaml
dependencies:
```

Example of **correct** code:

```dart
import 'package:a/a.dart';
```

```yaml
dependencies:
 a: ^1.0.0
```

## Further Reading

* [Linter for Dart - depend_on_referenced_packages](https://dart.dev/tools/linter-rules/depend_on_referenced_packages)