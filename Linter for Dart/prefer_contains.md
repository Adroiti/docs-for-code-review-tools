Pattern: Missing use of `contains`

Issue: -

## Description

Calling `indexOf` to see if a collection contains something is difficult to read and may have poor performance. Use `contains` instead.

Example of **correct** code:
```dart
if (!lunchBox.contains('sandwich') return 'so hungry...';
```

Example of **incorrect** code:
```dart
if (lunchBox.indexOf('sandwich') == -1 return 'so hungry...';
```

## Further Reading

* [Linter for Dart - prefer_contains](https://dart-lang.github.io/linter/lints/prefer_contains.html)