Pattern: Use of `await` for non-`Future`

Issue: -

## Description

**AVOID** using await on anything other than a future.

Example of **incorrect** code:
```dart
main() async {
 print(await 23);
}
```

Example of **correct** code:
```dart
main() async {
 print(await Future.value(23));
}
```

## Further Reading

* [Linter for Dart - await_only_futures](https://dart.dev/tools/linter-rules/await_only_futures)