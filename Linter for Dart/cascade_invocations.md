Pattern: Missing use of cascade invocation

Issue: -

## Description

**DO** Use the cascading style when successively invoking methods on the same reference.

Example of **incorrect** code:
```dart
SomeClass someReference = SomeClass();
someReference.firstMethod();
someReference.secondMethod();
```

Example of **incorrect** code:
```dart
SomeClass someReference = SomeClass();
...
someReference.firstMethod();
someReference.aProperty = value;
someReference.secondMethod();
```

Example of **correct** code:
```dart
SomeClass someReference = SomeClass()
  ..firstMethod()
  ..aProperty = value
  ..secondMethod();
```

Example of **correct** code:
```dart
SomeClass someReference = SomeClass();
...
someReference
  ..firstMethod()
  ..aProperty = value
  ..secondMethod();
```

## Further Reading

* [Linter for Dart - cascade_invocations](https://dart.dev/tools/linter-rules/cascade_invocations)