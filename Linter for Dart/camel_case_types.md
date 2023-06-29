Pattern: Malformed _UpperCamelCase_ for type name

Issue: -

## Description

Classes and typedefs should capitalize the first letter of each word (including the first word), and use no separators.

Example of **correct** code:
```dart
class SliderMenu {
 // ...
}

class HttpRequest {
 // ...
}

typedef num Adder(num x, num y);
```

## Further Reading

* [Linter for Dart - camel_case_types](https://dart.dev/tools/linter-rules/camel_case_types)
* [Effective Dart](https://dart.dev/guides/language/effective-dart/style/)