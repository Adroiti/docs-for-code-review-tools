Pattern: Use of setter without getter

Issue: -

## Description

Defining a setter without defining a corresponding getter can lead to logical
inconsistencies. Doing this could allow you to set a property to some value,
but then upon observing the property's value, it could easily be different.

Example of **incorrect** code:
```dart
class Bad {
 int l, r;

 set length(int newLength) {
  r = l + newLength;
 }
}
```

Example of **correct** code:
```dart
class Good {
 int l, r;

 int get length => r - l;

 set length(int newLength) {
  r = l + newLength;
 }
}
```

## Further Reading

* [Linter for Dart - avoid_setters_without_getters](https://dart-lang.github.io/linter/lints/avoid_setters_without_getters.html)