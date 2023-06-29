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

* [Linter for Dart - join_return_with_assignment](https://dart.dev/tools/linter-rules/join_return_with_assignment)