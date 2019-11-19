Pattern: Missing use of inlined list item declaration

Issue: -

## Description

Declare elements in list literals inline, rather than using `add` and `addAll` methods where possible.

Example of **incorrect** code:
```dart
var l = ['a']..add('b')..add('c');
var l2 = ['a']..addAll(['b', 'c'])
```

Example of **correct** code:
```dart
var l = ['a', 'b', 'c'];
var 2 = ['a', 'b', 'c'];
```

## Further Reading

* [Linter for Dart - prefer_inlined_adds](https://dart-lang.github.io/linter/lints/prefer_inlined_adds.html)