Pattern: Use of escaping inner quotes

Issue: -

## Description

Avoid escaping inner quotes by converting surrounding quotes.

Example of **incorrect** code:
```dart
var s = 'It\'s not fun';
```

Example of **correct** code:
```dart
var s = "It's not fun";
```

## Further Reading

* [Linter for Dart - avoid_escaping_inner_quotes](https://dart-lang.github.io/linter/lints/avoid_escaping_inner_quotes.html)