Pattern: Unnecessary getter

Issue: -

## Description

**PREFER** using a public final field instead of a private field with a public
getter.

If you have a field that outside code should be able to see but not assign to
(and you don't need to set it outside of the constructor), a simple solution
that works in many cases is to just mark it `final`.

Example of **correct** code:
```dart
class Box {
 final contents = [];
}
```

Example of **incorrect** code:
```dart
class Box {
 var _contents;
 get contents => _contents;
}
```

## Further Reading

* [Linter for Dart - unnecessary_getters_setters](https://dart.dev/tools/linter-rules/unnecessary_getters_setters)