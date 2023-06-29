Pattern: Dangling library doc comment

Issue: -

## Description

Attach library doc comments (with `///`) to library directives, rather than
leaving them dangling near the top of a library.

Example of **incorrect** code:
```dart
/// This is a great library.
import 'package:math';
```

```dart
/// This is a great library.

class C {}
```

Example of **correct** code:
```dart
/// This is a great library.
library;

import 'package:math';

class C {}
```

## Further Reading

* [Linter for Dart - dangling_library_doc_comments](https://dart.dev/tools/linter-rules/dangling_library_doc_comments)