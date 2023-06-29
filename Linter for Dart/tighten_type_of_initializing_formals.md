Pattern: Loose type of initializing formal

Issue: -

## Description

Tighten type of initializing formal if a non-null assert exists. This allows the
type system to catch problems rather than have them only be caught at run-time.

Example of **incorrect** code:

```dart
class A {
 A.c1(this.p) : assert(p != null);
 A.c2(this.p);
 final String? p;
}
```

Example of **correct** code:

```dart
class A {
 A.c1(String this.p) : assert(p != null);
 A.c2(this.p);
 final String? p;
}
```

## Further Reading

* [Linter for Dart - tighten_type_of_initializing_formals](https://dart.dev/tools/linter-rules/tighten_type_of_initializing_formals)