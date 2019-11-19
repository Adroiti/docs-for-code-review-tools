Pattern: Unnecessary getter/setter

Issue: -

## Description

In Java and C#, it's common to hide all fields behind getters and setters (or
properties in C#), even if the implementation just forwards to the field. That
way, if you ever need to do more work in those members, you can without needing
to touch the callsites. This is because calling a getter method is different
than accessing a field in Java, and accessing a property isn't binary-compatible
with accessing a raw field in C#.

Dart doesn't have this limitation. Fields and getters/setters are completely
indistinguishable. You can expose a field in a class and later wrap it in a
getter and setter without having to touch any code that uses that field.

Example of **correct** code:

```
class Box {
 var contents;
}
```

Example of **incorrect** code:

```
class Box {
 var _contents;
 get contents => _contents;
 set contents(value) {
  _contents = value;
 }
}
```

## Further Reading

* [Linter for Dart - unnecessary_getters_setters](https://dart-lang.github.io/linter/lints/unnecessary_getters_setters.html)