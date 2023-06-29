Pattern: Missing use of `close` for `dart.core.Sink`

Issue: -

## Description

Closing instances of `dart.core.Sink` prevents memory leaks and unexpected behavior.

Example of **incorrect** code:
```dart
class A {
 IOSink _sinkA;
 void init(filename) {
  _sinkA = new File(filename).openWrite(); // LINT
 }
}
```

Example of **incorrect** code:
```dart
void someFunction() {
 IOSink _sinkF; // LINT
}
```

Example of **correct** code:
```dart
class B {
 IOSink _sinkB;
 void init(filename) {
  _sinkB = new File(filename).openWrite(); // OK
 }

 void dispose(filename) {
  _sinkB.close();
 }
}
```

Example of **correct** code:
```dart
void someFunctionOK() {
 IOSink _sinkFOK; // OK
 _sinkFOK.close();
}
```

## Further Reading

* [Linter for Dart - close_sinks](https://dart.dev/tools/linter-rules/close_sinks)