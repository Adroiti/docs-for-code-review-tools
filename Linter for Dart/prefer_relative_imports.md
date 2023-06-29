Pattern: Missing use of relative import

Issue: -

## Description

When mixing relative and absolute imports it's possible to create confusion
where the same member gets imported in two different ways. One way to avoid
that is to ensure you consistently use relative imports for files withing the
`lib/` directory.

Example of **correct** code:

```
import 'bar.dart';
```

Example of **incorrect** code:

```
import 'package:my_package/bar.dart';
```

## Further Reading

* [Linter for Dart - prefer_relative_imports](https://dart.dev/tools/linter-rules/prefer_relative_imports)