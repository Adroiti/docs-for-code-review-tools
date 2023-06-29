Pattern: Use of `Iterable<E>.contains` with unrelated type

Issue: -

## Description

**DON'T** invoke `contains` on `Iterable` with an instance of different type
than the parameter type.

Doing this will invoke `==` on its elements and most likely will return `false`.

Example of **incorrect** code:
```dart
void someFunction() {
 var list = <int>[];
 if (list.contains('1')) print('someFunction'); // LINT
}
```

Example of **incorrect** code:
```dart
void someFunction3() {
 List<int> list = <int>[];
 if (list.contains('1')) print('someFunction3'); // LINT
}
```

Example of **incorrect** code:
```dart
void someFunction8() {
 List<DerivedClass2> list = <DerivedClass2>[];
 DerivedClass3 instance;
 if (list.contains(instance)) print('someFunction8'); // LINT
}
```

Example of **incorrect** code:
```dart
abstract class SomeIterable<E> implements Iterable<E> {}

abstract class MyClass implements SomeIterable<int> {
 bool badMethod(String thing) => this.contains(thing); // LINT
}
```

Example of **correct** code:
```dart
void someFunction10() {
 var list = [];
 if (list.contains(1)) print('someFunction10'); // OK
}
```

Example of **correct** code:
```dart
void someFunction1() {
 var list = <int>[];
 if (list.contains(1)) print('someFunction1'); // OK
}
```

Example of **correct** code:
```dart
void someFunction4() {
 List<int> list = <int>[];
 if (list.contains(1)) print('someFunction4'); // OK
}
```

Example of **correct** code:
```dart
void someFunction5() {
 List<ClassBase> list = <ClassBase>[];
 DerivedClass1 instance;
 if (list.contains(instance)) print('someFunction5'); // OK
}

abstract class ClassBase {}

class DerivedClass1 extends ClassBase {}
```

Example of **correct** code:
```dart
void someFunction6() {
 List<Mixin> list = <Mixin>[];
 DerivedClass2 instance;
 if (list.contains(instance)) print('someFunction6'); // OK
}

abstract class ClassBase {}

abstract class Mixin {}

class DerivedClass2 extends ClassBase with Mixin {}
```

Example of **correct** code:
```dart
void someFunction7() {
 List<Mixin> list = <Mixin>[];
 DerivedClass3 instance;
 if (list.contains(instance)) print('someFunction7'); // OK
}

abstract class ClassBase {}

abstract class Mixin {}

class DerivedClass3 extends ClassBase implements Mixin {}
```

## Further Reading

* [Linter for Dart - iterable_contains_unrelated_type](https://dart.dev/tools/linter-rules/iterable_contains_unrelated_type)