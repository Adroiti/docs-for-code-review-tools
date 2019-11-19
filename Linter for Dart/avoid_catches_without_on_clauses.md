Pattern: Use of `catch` without `on`

Issue: -

## Description

Using `catch` clauses without `on` clauses make your code prone to encountering
unexpected errors that won't be thrown (and thus will go unnoticed).

Example of **incorrect** code:
```dart
try {
 somethingRisky()
}
catch(e) {
 doSomething(e);
}
```

Example of **correct** code:
```dart
try {
 somethingRisky()
}
on Exception catch(e) {
 doSomething(e);
}
```

## Further Reading

* [Linter for Dart - avoid_catches_without_on_clauses](https://dart-lang.github.io/linter/lints/avoid_catches_without_on_clauses.html)