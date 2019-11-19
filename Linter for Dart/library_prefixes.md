Pattern: Invalid library prefix

Issue: -

## Description

**DO** use `lowercase_with_underscores` when specifying a library prefix.

Example of **correct** code:
```dart
import 'dart:math' as math;
import 'dart:json' as json;
import 'package:js/js.dart' as js;
import 'package:javascript_utils/javascript_utils.dart' as js_utils;
```

Example of **incorrect** code:
```dart
import 'dart:math' as Math;
import 'dart:json' as JSON;
import 'package:js/js.dart' as JS;
import 'package:javascript_utils/javascript_utils.dart' as jsUtils;
```

## Further Reading

* [Linter for Dart - library_prefixes](https://dart-lang.github.io/linter/lints/library_prefixes.html)