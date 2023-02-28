Pattern: Use of implicit `.call` tear off

Issue: -

## Description

**DO** explicitly tear off `.call` methods from objects when assigning to a Function
type. There is less magic with an explicit tear off. Future language versions
may remove the implicit call tear off.

Example of **incorrect** code:
```dart
class Callable {
 void call() {}
}
void callIt(void Function() f) {
 f();
}

callIt(Callable());
```

Example of **correct** code:
```dart
class Callable {
 void call() {}
}
void callIt(void Function() f) {
 f();
}

callIt(Callable().call);
```

## Further Reading

* [Linter for Dart - implicit_call_tearoffs](https://dart-lang.github.io/linter/lints/implicit_call_tearoffs.html)