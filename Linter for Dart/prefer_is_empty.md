Pattern: Missing use of `isEmpty`/`isNotEmpty`

Issue: -

## Description

The `Iterable` contract does not require that a collection know its length or be
able to provide it in constant time. Calling `length` just to see if the
collection contains anything can be slow.

Instead, there are faster and more readable getters: `isEmpty` and
`isNotEmpty`. Use the one that doesn't require you to negate the result.

Example of **correct** code:
```dart
if (lunchBox.isEmpty) return 'so hungry...';
if (words.isNotEmpty) return words.join(' ');
```

Example of **incorrect** code:
```dart
if (lunchBox.length == 0) return 'so hungry...';
if (words.length != 0) return words.join(' ');
```

## Further Reading

* [Linter for Dart - prefer_is_empty](https://dart.dev/tools/linter-rules/prefer_is_empty)