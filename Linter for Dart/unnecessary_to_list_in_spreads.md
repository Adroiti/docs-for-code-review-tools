Pattern: Unnecessary `toList()` in spread

Issue: -

## Description

Unnecessary `toList()` in spreads.

Example of **incorrect** code:
```dart
children: <Widget>[
 ...['foo', 'bar', 'baz'].map((String s) => Text(s)).toList(),
]
```

Example of **correct** code:
```dart
children: <Widget>[
 ...['foo', 'bar', 'baz'].map((String s) => Text(s)),
]
```

## Further Reading

* [Linter for Dart - unnecessary_to_list_in_spreads](https://dart-lang.github.io/linter/lints/unnecessary_to_list_in_spreads.html)