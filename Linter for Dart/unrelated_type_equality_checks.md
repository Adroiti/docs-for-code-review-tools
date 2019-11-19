Pattern: Unrelated type equality check

Issue: -

## Description

Comparing references of a type where neither is a subtype of the other most
likely will return `false` and might not reflect programmer's intent.

`Int64` and `Int32` from `package:fixnum` allow comparing to `int` provided
the `int` is on the right hand side. The lint allows this as a special case. 

Example of **incorrect** code:
```dart
void someFunction() {
 var x = '1';
 if (x == 1) print('someFunction'); // LINT
}
```

Example of **incorrect** code:
```dart
void someFunction1() {
 String x = '1';
 if (x == 1) print('someFunction1'); // LINT
}
```

Example of **incorrect** code:
```dart
void someFunction13(DerivedClass2 instance) {
 var other = new DerivedClass3();

 if (other == instance) print('someFunction13'); // LINT
}

class ClassBase {}

class DerivedClass1 extends ClassBase {}

abstract class Mixin {}

class DerivedClass2 extends ClassBase with Mixin {}

class DerivedClass3 extends ClassBase implements Mixin {}
```

Example of **correct** code:
```dart
void someFunction2() {
 var x = '1';
 var y = '2';
 if (x == y) print(someFunction2); // OK
}
```

Example of **correct** code:
```dart
void someFunction3() {
 for (var i = 0; i < 10; i++) {
  if (i == 0) print(someFunction3); // OK
 }
}
```

Example of **correct** code:
```dart
void someFunction4() {
 var x = '1';
 if (x == null) print(someFunction4); // OK
}
```

Example of **correct** code:
```dart
void someFunction7() {
 List someList;

 if (someList.length == 0) print('someFunction7'); // OK
}
```

Example of **correct** code:
```dart
void someFunction8(ClassBase instance) {
 DerivedClass1 other;

 if (other == instance) print('someFunction8'); // OK
}
```

Example of **correct** code:
```dart
void someFunction10(unknown) {
 var what = unknown - 1;
 for (var index = 0; index < unknown; index++) {
  if (what == index) print('someFunction10'); // OK
 }
}
```

Example of **correct** code:
```dart
void someFunction11(Mixin instance) {
 var other = new DerivedClass2();

 if (other == instance) print('someFunction11'); // OK
 if (other != instance) print('!someFunction11'); // OK
}

class ClassBase {}

abstract class Mixin {}

class DerivedClass2 extends ClassBase with Mixin {}
```

## Further Reading

* [Linter for Dart - unrelated_type_equality_checks](https://dart-lang.github.io/linter/lints/unrelated_type_equality_checks.html)