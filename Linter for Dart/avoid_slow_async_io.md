Pattern: Use of slow async `dart:io` method

Issue: -

## Description

**AVOID** using the following asynchronous file I/O methods because they are
much slower than their synchronous counterparts.

* `Directory.exists`
* `Directory.stat`
* `File.lastModified`
* `File.exists`
* `File.stat`
* `FileSystemEntity.isDirectory`
* `FileSystemEntity.isFile`
* `FileSystemEntity.isLink`
* `FileSystemEntity.type`

Example of **incorrect** code:
```dart
import 'dart:io';

Future<Null> someFunction() async {
 var file = new File('/path/to/my/file');
 var now = new DateTime.now();
 if ((await file.lastModified()).isBefore(now)) print('before'); // LINT
}
```

Example of **correct** code:
```dart
import 'dart:io';

Future<Null> someFunction() async {
 var file = new File('/path/to/my/file');
 var now = new DateTime.now();
 if (file.lastModifiedSync().isBefore(now)) print('before'); // OK
}
```

## Further Reading

* [Linter for Dart - avoid_slow_async_io](https://dart.dev/tools/linter-rules/avoid_slow_async_io)