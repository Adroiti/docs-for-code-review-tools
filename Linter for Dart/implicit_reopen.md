Pattern: Implicit reopen

Issue: -

## Description

Using an `interface`, `base`, `final`, or `sealed` modifier on a class,
or a `base` modifier on a mixin,
authors can control whether classes and mixins allow being implemented,
extended, and/or mixed in from outside of the library where they're defined.
In some cases, it's possible for an author to inadvertently relax these controls
and implicitly "reopen" a class. (A similar reopening cannot occur with a mixin.)

This lint guards against unintentionally reopening a class by requiring such
cases to be made explicit with the 
[`@reopen`](https://pub.dev/documentation/meta/latest/meta/reopen-constant.html)
annotation in `package:meta`.

Example of **incorrect** code:
```dart
interface class I {}

class C extends I {} // LINT
```

Example of **correct** code:
```dart
interface class I {}

final class C extends I {}
```

```dart
interface class I {}

final class C extends I {}
```

```dart
import 'package:meta/meta.dart';

interface class I {}

@reopen
class C extends I {}
```

## Further Reading

* [Linter for Dart - implicit_reopen](https://dart.dev/tools/linter-rules/implicit_reopen)