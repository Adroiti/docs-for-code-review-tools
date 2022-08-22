Pattern: Invoking async function on non-anync block

Issue: -

## Description

Making asynchronous calls in non-`async` functions is usually the sign of a
programming error. In general these functions should be marked `async` and such
futures should likely be awaited (as enforced by `unawaited_futures`).

**DON'T** invoke asynchronous functions in non-`async` blocks.

Example of **incorrect** code:

```dart
void recreateDir(String path) {
 deleteDir(path);
 createDir(path);
}

Future<void> deleteDir(String path) async {}

Future<void> createDir(String path) async {}
```

Example of **correct** code:

```dart
Future<void> recreateDir(String path) async {
 await deleteDir(path);
 await createDir(path);
}

Future<void> deleteDir(String path) async {}

Future<void> createDir(String path) async {}
```

## Further Reading

* [Linter for Dart - discarded_futures](https://dart-lang.github.io/linter/lints/discarded_futures.html)