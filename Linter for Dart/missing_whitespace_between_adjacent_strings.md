Pattern: Missing whitespace between adjacent strings

Issue: -

## Description

Add a trailing whitespace to prevent missing whitespace between adjacent
strings.

With long text split across adjacent strings it's easy to forget a whitespace
between strings.

Example of **incorrect** code:
```dart
var s =
 'Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed'
 'do eiusmod tempor incididunt ut labore et dolore magna';
```

Example of **correct** code:
```dart
var s =
 'Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed '
 'do eiusmod tempor incididunt ut labore et dolore magna';
```

## Further Reading

* [Linter for Dart - missing_whitespace_between_adjacent_strings](https://dart.dev/tools/linter-rules/missing_whitespace_between_adjacent_strings)