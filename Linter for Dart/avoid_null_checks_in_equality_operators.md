Pattern: Use of null check in custom `==` operator

Issue: -

## Description

As null is a special type, no class can be equivalent to it. Thus, it is
redundant to check whether the other instance is null. 

Example of **incorrect** code:
```dart
class Person {
 final String name;

 @override
 operator ==(other) =>
   other != null && other is Person && name == other.name;
}
```

Example of **correct** code:
```dart
class Person {
 final String name;

 @override
 operator ==(other) => other is Person && name == other.name;
}
```

## Further Reading

* [Linter for Dart - avoid_null_checks_in_equality_operators](https://dart.dev/tools/linter-rules/avoid_null_checks_in_equality_operators)