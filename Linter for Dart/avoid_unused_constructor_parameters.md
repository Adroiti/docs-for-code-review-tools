Pattern: Unused constructor parameter

Issue: -

## Description

**AVOID** defining unused parameters in constructors.

Example of **incorrect** code:
```dart
class BadOne {
 BadOne(int unusedParameter, [String unusedPositional]);
}

class BadTwo {
 int c;

 BadTwo(int a, int b, int x) {
  c = a + b;
 }
}
```

## Further Reading

* [Linter for Dart - avoid_unused_constructor_parameters](https://dart-lang.github.io/linter/lints/avoid_unused_constructor_parameters.html)