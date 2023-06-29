Pattern: Use of function literal in `forEach`

Issue: -

## Description

**AVOID** using `forEach` with a function literal.

Example of **incorrect** code:
```dart
people.forEach((person) {
 ...
});
```

Example of **correct** code:
```dart
for (var person in people) {
 ...
}

people.forEach(print);
```

## Further Reading

* [Linter for Dart - avoid_function_literals_in_foreach_calls](https://dart.dev/tools/linter-rules/avoid_function_literals_in_foreach_calls)