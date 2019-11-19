Pattern: Use of initialize to null

Issue: -

## Description

In Dart, a variable or field that is not explicitly initialized automatically
gets initialized to null. This is reliably specified by the language. There's
no concept of "uninitialized memory" in Dart. Adding `= null` is redundant and
unneeded.

Example of **correct** code:
```dart
int _nextId;

class LazyId {
 int _id;

 int get id {
  if (_nextId == null) _nextId = 0;
  if (_id == null) _id = _nextId++;

  return _id;
 }
}
```

Example of **incorrect** code:
```dart
int _nextId = null;

class LazyId {
 int _id = null;

 int get id {
  if (_nextId == null) _nextId = 0;
  if (_id == null) _id = _nextId++;

  return _id;
 }
}
```

## Further Reading

* [Linter for Dart - avoid_init_to_null](https://dart-lang.github.io/linter/lints/avoid_init_to_null.html)
* [Effective dart](https://dart.dev/guides/language/effective-dart/usage#dont-explicitly-initialize-variables-to-null)