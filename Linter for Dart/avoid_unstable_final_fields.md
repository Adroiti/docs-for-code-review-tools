Pattern: Use of unstable final field

Issue: -

## Description

**AVOID** overriding or implementing a final field as a getter which could
return different values if it is invoked multiple times on the same receiver.
This could occur because the getter is an implicitly induced getter of a
non-final field, or it could be an explicitly declared getter with a body
that isn't known to return the same value each time it is called.

The underlying motivation for this rule is that if it is followed then a final
field is an immutable property of an object. This is important for correctness
because it is then safe to assume that the value does not change during the
execution of an algorithm. In contrast, it may be necessary to re-check any
other getter repeatedly if it is not known to have this property. Similarly,
it is safe to cache the immutable property in a local variable and promote it,
but for any other property it is necessary to check repeatedly that the
underlying property hasn't changed since it was promoted.

Example of **incorrect** code:
```dart
class A {
 final int i;
 A(this.i);
}

var j = 0;

class B1 extends A {
 int get i => ++j + super.i; // LINT.
 B1(super.i);
}

class B2 implements A {
 int i; // LINT.
 B2(this.i);
}
```

Example of **correct** code:

```dart
class C {
 final int i;
 C(this.i);
}

class D1 implements C {
 late final int i = someExpression; // OK.
}

class D2 extends C {
 int get i => super.i + 1; // OK.
 D2(super.i);
}

class D3 implements C {
 final int i; // OK.
 D3(this.i);
}
```

## Further Reading

* [Linter for Dart - avoid_unstable_final_fields](https://dart.dev/tools/linter-rules/avoid_unstable_final_fields)