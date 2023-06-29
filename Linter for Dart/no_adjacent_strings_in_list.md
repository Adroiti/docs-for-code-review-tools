Pattern: Use of adjacent string in list

Issue: -

## Description

This can be sign of forgotten comma.

Example of **correct** code:
```dart
List<String> list = <String>[
 'a' +
 'b',
 'c',
];
```

Example of **incorrect** code:
```dart
List<String> list = <String>[
 'a'
 'b',
 'c',
];
```

## Further Reading

* [Linter for Dart - no_adjacent_strings_in_list](https://dart.dev/tools/linter-rules/no_adjacent_strings_in_list)