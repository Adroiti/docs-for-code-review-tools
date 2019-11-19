Pattern: Unnecessary statement

Issue: -

## Description

Statements which have no clear effect are usually unnecessary, or should be broken up.

Example of **incorrect** code:
```dart
myvar;
list.clear;
1 + 2;
methodOne() + methodTwo();
foo ? bar : baz;
```

Though the added methods have a clear effect, the addition itself does not
unless there is some magical overload of the `+` operator.

Usually code like this indicates an incomplete thought, and is a bug.

Example of **correct** code:
```dart
some.method();
new SomeClass();
methodOne();
methodTwo();
foo ? bar() : baz();
return myvar;
```

## Further Reading

* [Linter for Dart - unnecessary_statements](https://dart-lang.github.io/linter/lints/unnecessary_statements.html)