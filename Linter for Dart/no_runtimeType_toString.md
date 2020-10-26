Pattern: Calling `toString` on runtime type

Issue: -

## Description

Calling `toString` on a runtime type is a non-trivial operation that can
negatively impact performance. It's better to avoid it.

Example of **incorrect** code:

```dart
class A {
 String toString() => '$runtimeType()';
}
```

Example of **correct** code:

```dart
class A {
 String toString() => 'A()';
}
```

This lint has some exceptions where performance is not a problem or where real
type information is more important than performance:

* in assertion
* in throw expressions
* in catch clauses
* in mixin declaration
* in abstract class

## Further Reading

* [Linter for Dart - no_runtimeType_toString](https://dart-lang.github.io/linter/lints/no_runtimeType_toString.html)