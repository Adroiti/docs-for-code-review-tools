Pattern: Malformed _UpperCamelCase_ for extension name

Issue: -

## Description

Extensions should capitalize the first letter of each word (including the first word), and use no separators.

Example of **correct** code:
```dart
extension MyFancyList<T> on List<T> { 
 // ... 
}

extension SmartIterable<T> on Iterable<T> {
 // ...
}
```

## Further Reading

* [Linter for Dart - camel_case_extensions](https://dart-lang.github.io/linter/lints/camel_case_extensions.html)