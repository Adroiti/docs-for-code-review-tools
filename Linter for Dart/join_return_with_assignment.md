Pattern: Missing join for return with assignment

Issue: -

## Description

**DO** join return statement with assignment when possible.

Example of **incorrect** code:
```dart
class A {
 B _lazyInstance;
 static B get instance {
  _lazyInstance ??= new B(); // LINT
  return _lazyInstance;
 }
}
```

Example of **correct** code:
```dart
class A {
 B _lazyInstance;
 static B get instance => _lazyInstance ??= new B();
}
```

## Further Reading

* [Linter for Dart - join_return_with_assignment](https://dart-lang.github.io/linter/lints/join_return_with_assignment.html)