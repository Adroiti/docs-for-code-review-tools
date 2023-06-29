Pattern: Missing use of `isNotEmpty` for `Iterable`/`Map`

Issue: -

## Description

When testing whether an `Iterable` or `Map` is empty, prefer `isNotEmpty` over `!isEmpty` to improve code readability.

Example of **correct** code:
```dart
if (todo.isNotEmpty) {
 sendResults(request, todo.isEmpty);
}
```

Example of **incorrect** code:
```dart
if (!sources.isEmpty) {
 process(sources);
}
```

## Further Reading

* [Linter for Dart - prefer_is_not_empty](https://dart.dev/tools/linter-rules/prefer_is_not_empty)