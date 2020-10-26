Pattern: Use of `<Type>.toString()`

Issue: -

## Description

**DO** avoid calls to `<Type>.toString()` in production code, since it does not
contractually return the user-defined name of the Type (or underlying class).
Development-mode compilers where code size is not a concern use the full name,
but release-mode compilers often choose to minify these symbols.

Example of **incorrect** code:

```dart
void bar(Object other) {
 if (other.runtimeType.toString() == 'Bar') {
  doThing();
 }
}

Object baz(Thing myThing) {
 return getThingFromDatabase(key: myThing.runtimeType.toString());
}
```

Example of **correct** code:

```dart
void bar(Object other) {
 if (other is Bar) {
  doThing();
 }
}

class Thing {
 String get thingTypeKey => ...
}

Object baz(Thing myThing) {
 return getThingFromDatabase(key: myThing.thingTypeKey);
}
```

## Further Reading

* [Linter for Dart - avoid_type_to_string](https://dart-lang.github.io/linter/lints/avoid_type_to_string.html)