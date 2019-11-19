Pattern: Use of relative lib import

Issue: -

## Description

When mixing relative and absolute imports it's possible to create confusion
where the same member gets imported in two different ways. An easy way to avoid
that is to ensure you have no relative imports that include `lib/` in their
paths.

Example of **correct** code:

```
import 'package:foo/bar.dart';

import 'baz.dart';

...
```

Example of **incorrect** code:

```
import 'package:foo/bar.dart';

import '../lib/baz.dart';

...
```

## Further Reading

* [Linter for Dart - avoid_relative_lib_imports](https://dart-lang.github.io/linter/lints/avoid_relative_lib_imports.html)