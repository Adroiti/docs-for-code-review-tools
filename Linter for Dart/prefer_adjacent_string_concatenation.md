Pattern: Missing use of adjacent strings for concatenation

Issue: -

## Description

**DO** use adjacent strings to concatenate string literals.

Example of **incorrect** code:
```dart
raiseAlarm(
  'ERROR: Parts of the spaceship are on fire. Other ' +
  'parts are overrun by martians. Unclear which are which.');
```

Example of **correct** code:
```dart
raiseAlarm(
  'ERROR: Parts of the spaceship are on fire. Other '
  'parts are overrun by martians. Unclear which are which.');
```

## Further Reading

* [Linter for Dart - prefer_adjacent_string_concatenation](https://dart.dev/tools/linter-rules/prefer_adjacent_string_concatenation)