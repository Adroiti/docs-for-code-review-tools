Pattern: Missing use of `=>`

Issue: -

## Description

**CONSIDER** using `=>` for short members whose body is a single return statement.

Example of **incorrect** code:
```dart
get width {
 return right - left;
}
```

Example of **incorrect** code:
```dart
bool ready(num time) {
 return minTime == null || minTime <= time;
}
```

Example of **incorrect** code:
```dart
containsValue(String value) {
 return getValues().contains(value);
}
```

Example of **correct** code:
```dart
get width => right - left;
```

Example of **correct** code:
```dart
bool ready(num time) => minTime == null || minTime <= time;
```

Example of **correct** code:
```dart
containsValue(String value) => getValues().contains(value);
```

## Further Reading

* [Linter for Dart - prefer_expression_function_bodies](https://dart-lang.github.io/linter/lints/prefer_expression_function_bodies.html)