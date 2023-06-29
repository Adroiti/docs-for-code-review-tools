Pattern: Unnecessary `override`

Issue: -

## Description

**DON'T** override a method to do a super method invocation with same parameters.

Example of **incorrect** code:
```dart
class A extends B {
 @override
 void foo() {
  super.foo();
 }
}
```

Example of **correct** code:
```dart
class A extends B {
 @override
 void foo() {
  doSomethingElse();
 }
}
```

It's valid to override a member in the following cases:

* if a type (return type or a parameter type) is not the exactly the same as the
super method,
* if the `covariant` keyword is added to one of the parameters,
* if documentation comments are present on the member,
* if the member has annotations other than `@override`.

`noSuchMethod` is a special method and is not checked by this rule.

## Further Reading

* [Linter for Dart - unnecessary_overrides](https://dart.dev/tools/linter-rules/unnecessary_overrides)