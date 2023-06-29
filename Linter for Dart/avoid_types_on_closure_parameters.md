Pattern: Use of type on closure parameter

Issue: -

## Description

Annotating types for function expression parameters is usually unnecessary
because the parameter types can almost always be inferred from the context,
thus making the practice redundant.

Example of **incorrect** code:
```dart
var names = people.map((Person person) => person.name);
```

Example of **correct** code:
```dart
var names = people.map((person) => person.name);
```

## Further Reading

* [Linter for Dart - avoid_types_on_closure_parameters](https://dart.dev/tools/linter-rules/avoid_types_on_closure_parameters)