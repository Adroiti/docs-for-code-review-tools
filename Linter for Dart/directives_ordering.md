Pattern: Wrong directive order

Issue: -

## Description

**DO** place “dart:” imports before other imports.

Example of **incorrect** code:
```dart
import 'package:bar/bar.dart';
import 'package:foo/foo.dart';

import 'dart:async'; // LINT
import 'dart:html'; // LINT
```

Example of **incorrect** code:
```dart
import 'dart:html'; // OK
import 'package:bar/bar.dart';

import 'dart:async'; // LINT
import 'package:foo/foo.dart';
```

Example of **correct** code:
```dart
import 'dart:async'; // OK
import 'dart:html'; // OK

import 'package:bar/bar.dart';
import 'package:foo/foo.dart';
```

**DO** place “package:” imports before relative imports.

Example of **incorrect** code:
```dart
import 'a.dart';
import 'b.dart';

import 'package:bar/bar.dart'; // LINT
import 'package:foo/foo.dart'; // LINT
```
Example of **incorrect** code:
```dart
import 'package:bar/bar.dart'; // OK
import 'a.dart';

import 'package:foo/foo.dart'; // LINT
import 'b.dart';
```

Example of **correct** code:
```dart
import 'package:bar/bar.dart'; // OK
import 'package:foo/foo.dart'; // OK

import 'a.dart';
import 'b.dart';
```

**PREFER** placing “third-party” “package:” imports before other imports.

Example of **incorrect** code:
```dart
import 'package:myapp/io.dart';
import 'package:myapp/util.dart';

import 'package:bar/bar.dart'; // LINT
import 'package:foo/foo.dart'; // LINT
```

Example of **correct** code:
```dart
import 'package:bar/bar.dart'; // OK
import 'package:foo/foo.dart'; // OK

import 'package:myapp/io.dart';
import 'package:myapp/util.dart';
```

**DO** specify exports in a separate section after all imports.

Example of **incorrect** code:
```dart
import 'src/error.dart';
export 'src/error.dart'; // LINT
import 'src/string_source.dart';
```

Example of **correct** code:
```dart
import 'src/error.dart';
import 'src/string_source.dart';

export 'src/error.dart'; // OK
```

**DO** sort sections alphabetically.

Example of **incorrect** code:
```dart
import 'package:foo/bar.dart'; // OK
import 'package:bar/bar.dart'; // LINT

import 'a/b.dart'; // OK
import 'a.dart'; // LINT
```

Example of **correct** code:
```dart
import 'package:bar/bar.dart'; // OK
import 'package:foo/bar.dart'; // OK

import 'a.dart'; // OK
import 'a/b.dart'; // OK
```

## Further Reading

* [Linter for Dart - directives_ordering](https://dart.dev/tools/linter-rules/directives_ordering)
* [Effective Dart](https://dart.dev/guides/language/effective-dart/style#ordering)