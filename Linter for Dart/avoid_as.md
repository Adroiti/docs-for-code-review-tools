Pattern: Use of `as`

Issue: -

## Description

If you know the type is correct, use an assertion or assign to a more
narrowly-typed variable (this avoids the type check in release mode; `as` is not
compiled out in release mode). If you don't know whether the type is
correct, check using `is` (this avoids the exception that `as` raises).

Example of **incorrect** code:
```dart
(pm as Person).firstName = 'Seth';
```

Example of **correct** code:
```dart
Person person = pm;
person.firstName = 'Seth';
```

or

Example of **correct** code:
```dart
if (pm is Person)
 pm.firstName = 'Seth';
```

but certainly not

Example of **incorrect** code:
```dart
try {
  (pm as Person).firstName = 'Seth';
} on CastError { }

```

Note that an exception is made in the case of `dynamic` since the cast has no
performance impact.

**OK:**
```dart
HasScrollDirection scrollable = renderObject as dynamic;
```

## Further Reading

* [Linter for Dart - avoid_as](https://dart.dev/tools/linter-rules/avoid_as)