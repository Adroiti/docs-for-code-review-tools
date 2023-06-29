Pattern: Throw in `finally`

Issue: -

## Description

Throwing exceptions in finally blocks will inevitably cause unexpected behavior that is hard to debug.

Example of **correct** code:
```dart
class Ok {
 double compliantMethod() {
  var i = 5;
  try {
   i = 1 / 0;
  } catch (e) {
   print(e); // OK
  }
  return i;
 }
}
```

Example of **incorrect** code:
```dart
class BadThrow {
 double nonCompliantMethod() {
  try {
   print('hello world! ${1 / 0}');
  } catch (e) {
   print(e);
  } finally {
   throw 'Find the hidden error :P'; // LINT
  }
 }
}
```

## Further Reading

* [Linter for Dart - throw_in_finally](https://dart.dev/tools/linter-rules/throw_in_finally)