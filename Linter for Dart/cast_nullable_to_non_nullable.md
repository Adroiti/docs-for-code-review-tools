Pattern: Casting nullable to non-nullable type

Issue: -

## Description

Don't cast a nullable value to a non-nullable type. This hides a null check
and most of the time it is not what is expected.

Example of **incorrect** code:

```dart
class A {}
class B extends A {}

A? a;
var v = a as B;
var v = a as A;
```

Example of **correct** code:

```dart
class A {}
class B extends A {}

A? a;
var v = a! as B;
var v = a!;
```

## Further Reading

* [Linter for Dart - cast_nullable_to_non_nullable](https://dart.dev/tools/linter-rules/cast_nullable_to_non_nullable)