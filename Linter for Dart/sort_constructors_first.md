Pattern: Unsorted constructor declarations

Issue: -

## Description

**DO** sort constructor declarations before other members.

Example of **correct** code:
```dart
abstract class Animation<T> {
 const Animation(this.value);
 double value;
 void addListener(VoidCallback listener);
}
```

Example of **incorrect** code:
```dart
abstract class Visitor {
 double value;
 visitSomething(Something s);
 Visitor();
}
```

## Further Reading

* [Linter for Dart - sort_constructors_first](https://dart-lang.github.io/linter/lints/sort_constructors_first.html)