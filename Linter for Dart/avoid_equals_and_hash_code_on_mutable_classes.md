Pattern: Defining custom equality for mutable class

Issue: -

## Description

If a class is mutable, overloading operator `==` and `hashCode` can lead to unpredictable and undesirable behavior when used in collections.

When you define `==`, you also have to define `hashCode`. Both of those should take into account the object’s fields. If those fields change then that implies the object’s hash code can change. Most hash-based collections don’t anticipate that—they assume an object’s hash code will be the same forever and may behave unpredictably if that isn’t true.

Example of **correct** code:
```dart
@immutable
class A {
 final String key;
 const A(this.key);
 @override
 operator ==(other) => other is A && other.key == key;
 @override
 int hashCode() => key.hashCode;
}
```

Example of **incorrect** code:
```dart
class B {
 String key;
 const B(this.key);
 @override
 operator ==(other) => other is B && other.key == key;
 @override
 int hashCode() => key.hashCode;
}
```

NOTE: The lint checks the use of the `@immutable` annotation, and will trigger
even if the class is otherwise not mutable. Thus:

Example of **incorrect** code:
```dart
class C {
 final String key;
 const C(this.key);
 @override
 operator ==(other) => other is B && other.key == key;
 @override
 int hashCode() => key.hashCode;
}
```

## Further Reading

* [Linter for Dart - avoid_equals_and_hash_code_on_mutable_classes](https://dart.dev/tools/linter-rules/avoid_equals_and_hash_code_on_mutable_classes)
* [Effective Dart](https://dart.dev/guides/language/effective-dart/design#avoid-defining-custom-equality-for-mutable-classes)