Pattern: Missing use of library directive for annotation

Issue: -

## Description

Attach library annotations to library directives, rather than some other library-level element.

Example of **incorrect** code:
```dart
@TestOn('browser')

import 'package:test/test.dart';

void main() {}
```

Example of **correct** code:
```dart
@TestOn('browser')
library;

import 'package:test/test.dart';

void main() {}
```

## Further Reading

* [Linter for Dart - library_annotations](https://dart.dev/tools/linter-rules/library_annotations)