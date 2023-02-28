Pattern: Use of collection method with unrelated type

Issue: -

## Description

**DON'T** invoke certain collection method with an argument with an unrelated
type.

Doing this will invoke `==` on the collection's elements and most likely will
return `false`.

An argument passed to a collection method should relate to the collection type
as follows:

* an argument to `Iterable<E>.contains` should be related to `E`
* an argument to `List<E>.remove` should be related to `E`
* an argument to `Map<K, V>.containsKey` should be related to `K`
* an argument to `Map<K, V>.containsValue` should be related to `V`
* an argument to `Map<K, V>.remove` should be related to `K`
* an argument to `Map<K, V>.[]` should be related to `K`
* an argument to `Queue<E>.remove` should be related to `E`
* an argument to `Set<E>.lookup` should be related to `E`
* an argument to `Set<E>.remove` should be related to `E`

Example of **incorrect** code:
```dart
void someFunction() {
 var list = <int>[];
 if (list.contains('1')) print('someFunction'); // LINT
}
```

Example of **incorrect** code:
```dart
void someFunction() {
 var set = <int>{};
 set.remove('1'); // LINT
}
```

Example of **correct** code:
```dart
void someFunction() {
 var list = <int>[];
 if (list.contains(1)) print('someFunction'); // OK
}
```

Example of **correct** code:
```dart
void someFunction() {
 var set = <int>{};
 set.remove(1); // OK
}
```

## Further Reading

* [Linter for Dart - collection_methods_unrelated_type](https://dart-lang.github.io/linter/lints/collection_methods_unrelated_type.html)