Pattern: Invalid non-constant identifier name

Issue: -

## Description

Class members, top-level definitions, variables, parameters, named parameters
and named constructors should capitalize the first letter of each word
except the first word, and use no separators.

Example of **correct** code:
```dart
var item;

HttpRequest httpRequest;

align(clearItems) {
 // ...
}
```

## Further Reading

* [Linter for Dart - non_constant_identifier_names](https://dart-lang.github.io/linter/lints/non_constant_identifier_names.html)