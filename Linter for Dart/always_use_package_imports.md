Pattern: Missing use of package import

Issue: -

## Description

*DO* avoid relative imports for files in `lib/`.

When mixing relative and absolute imports it's possible to create confusion
where the same member gets imported in two different ways. One way to avoid
that is to ensure you consistently use absolute imports for files withing the
`lib/` directory.

This is the opposite of 'prefer_relative_imports'.
Might be used with 'avoid_relative_lib_imports' to avoid relative imports of
files within `lib/` directory outside of it. (for example `test/`)

Example of **correct** code:

```
import 'package:foo/bar.dart';

import 'package:foo/baz.dart';

import 'package:foo/src/baz.dart';
...
```

Example of **incorrect** code:

```
import 'baz.dart';

import 'src/bag.dart'

import '../lib/baz.dart';

...
```

## Further Reading

* [Linter for Dart - always_use_package_imports](https://dart.dev/tools/linter-rules/always_use_package_imports)