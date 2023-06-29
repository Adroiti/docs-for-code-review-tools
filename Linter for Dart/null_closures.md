Pattern: Use of `null` as argument where closure is expected

Issue: -

## Description

Often a closure that is passed to a method will only be called conditionally,
so that tests and "happy path" production calls do not reveal that `null` will
result in an exception being thrown.

This rule only catches null literals being passed where closures are expected
in the following locations:

#### Constructors

* From `dart:async`
 * `Future` at the 0th positional parameter
 * `Future.microtask` at the 0th positional parameter
 * `Future.sync` at the 0th positional parameter
 * `Timer` at the 0th positional parameter
 * `Timer.periodic` at the 1st positional parameter
* From `dart:core`
 * `List.generate` at the 1st positional parameter

#### Static functions

* From `dart:async`
 * `sheduleMicrotask` at the 0th positional parameter
 * `Future.doWhile` at the 0th positional parameter
 * `Future.forEach` at the 0th positional parameter
 * `Future.wait` at the named parameter `cleanup`
 * `Timer.run` at the 0th positional parameter

#### Instance methods

* From `dart:async`
 * `Future.then` at the 0th positional parameter
 * `Future.complete` at the 0th positional parameter
* From `dart:collection`
 * `Queue.removeWhere` at the 0th positional parameter
 * `Queue.retain
 * `Iterable.firstWhere` at the 0th positional parameter, and the named
  parameter `orElse`
 * `Iterable.forEach` at the 0th positional parameter
 * `Iterable.fold` at the 1st positional parameter
 * `Iterable.lastWhere` at the 0th positional parameter, and the named
  parameter `orElse`
 * `Iterable.map` at the 0th positional parameter
 * `Iterable.reduce` at the 0th positional parameter
 * `Iterable.singleWhere` at the 0th positional parameter
 * `Iterable.skipWhile` at the 0th positional parameter
 * `Iterable.takeWhile` at the 0th positional parameter
 * `Iterable.where` at the 0th positional parameter
 * `List.removeWhere` at the 0th positional parameter
 * `List.retainWhere` at the 0th positional parameter
 * `String.replaceAllMapped` at the 1st positional parameter
 * `String.replaceFirstMapped` at the 1st positional parameter
 * `String.splitMapJoin` at the named parameters `onMatch` and `onNonMatch`

Example of **incorrect** code:
```dart
[1, 3, 5].firstWhere((e) => e.isOdd, orElse: null);
```

Example of **correct** code:
```dart
[1, 3, 5].firstWhere((e) => e.isOdd, orElse: () => null);
```

## Further Reading

* [Linter for Dart - null_closures](https://dart.dev/tools/linter-rules/null_closures)