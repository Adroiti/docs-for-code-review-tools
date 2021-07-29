Pattern: Inconsistent use of `@Deprecated()`

Issue: -

## Description

Do apply `@Deprecated()` consistently:

- if a class is deprecated, its constructors should also be deprecated.
- if a field is deprecated, the constructor parameter pointing to it should also be deprecated.
- if a constructor parameter pointing to a field is deprecated, the field should also be deprecated.

Example of **incorrect** code:

```dart
@deprecated
class A {
 A();
}

class B {
 B({this.field});
 @deprecated
 Object field;
}
```

Example of **correct** code:

```dart
@deprecated
class A {
 @deprecated
 A();
}

class B {
 B({@deprecated this.field});
 @deprecated
 Object field;
}
```

## Further Reading

* [Linter for Dart - deprecated_consistency](https://dart-lang.github.io/linter/lints/deprecated_consistency.html)