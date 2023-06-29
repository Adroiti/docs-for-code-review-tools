Pattern: Missing use of `cancel` for `dart.async.StreamSubscription`

Issue: -

## Description

Canceling instances of `StreamSubscription` prevents memory leaks and unexpected behavior.

Example of **incorrect** code:
```dart
class A {
 StreamSubscription _subscriptionA; // LINT
 void init(Stream stream) {
  _subscriptionA = stream.listen((_) {});
 }
}
```

Example of **incorrect** code:
```dart
void someFunction() {
 StreamSubscription _subscriptionF; // LINT
}
```

Example of **correct** code:
```dart
class B {
 StreamSubscription _subscriptionB; // OK
 void init(Stream stream) {
  _subscriptionB = stream.listen((_) {});
 }

 void dispose(filename) {
  _subscriptionB.cancel();
 }
}
```

Example of **correct** code:
```dart
void someFunctionOK() {
 StreamSubscription _subscriptionB; // OK
 _subscriptionB.cancel();
}
```

## Further Reading

* [Linter for Dart - cancel_subscriptions](https://dart.dev/tools/linter-rules/cancel_subscriptions)