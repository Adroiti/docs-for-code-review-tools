Pattern: Missing leading newline for multi-line string

Issue: -

## Description

Multi-line strings are easier to read when they start with a newline (a newline
starting a multi-line string is ignored).

Example of **incorrect** code:

```dart
var s1 = '''{
  "a": 1,
  "b": 2
}''';
```

Example of **correct** code:
```dart
var s1 = '''
{
  "a": 1,
  "b": 2
}''';

var s2 = '''This onliner multiline string is ok. It usually allows to escape both ' and " in the string.''';
```

## Further Reading

* [Linter for Dart - leading_newlines_in_multiline_strings](https://dart-lang.github.io/linter/lints/leading_newlines_in_multiline_strings.html)