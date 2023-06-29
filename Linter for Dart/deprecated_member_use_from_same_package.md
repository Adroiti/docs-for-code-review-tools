Pattern: Deprecated member use from same package

Issue: -

## Description

Elements which are annotated with `@deprecated` should not be referenced from
within the package in which they are declared.

**AVOID** using deprecated elements.

Example of **incorrect** code:
```dart
// Declared in one library:
class Foo {
 @Deprecated("Use 'm2' instead")
 void m1() {}

 void m2({
   @Deprecated('This is an old parameter') int? p,
 })
}

@Deprecated('Do not use')
int x = 0;

// In the same or another library, but within the same package:
void m(Foo foo) {
 foo.m1();
 foo.m2(p: 7);
 x = 1;
}
```

Deprecated elements can be used from within _other_ deprecated elements, in
order to allow for the deprecation of a collection of APIs together as one unit.

Example of **correct** code:
```dart
// Declared in one library:
class Foo {
 @Deprecated("Use 'm2' instead")
 void m1() {}

 void m2({
   @Deprecated('This is an old parameter') int? p,
 })
}

@Deprecated('Do not use')
int x = 0;

// In the same or another library, but within the same package:
@Deprecated('Do not use')
void m(Foo foo) {
 foo.m1();
 foo.m2(p: 7);
 x = 1;
}
```

## Further Reading

* [Linter for Dart - deprecated_member_use_from_same_package](https://dart.dev/tools/linter-rules/deprecated_member_use_from_same_package)