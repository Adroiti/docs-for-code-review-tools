Pattern: Use of one-member abstract class

Issue: -

## Description

Unlike Java, Dart has first-class functions, closures, and a nice light syntax
for using them. If all you need is something like a callback, just use a
function. If you're defining a class and it only has a single abstract member
with a meaningless name like `call` or `invoke`, there is a good chance
you just want a function.

Example of **correct** code:
```dart
typedef bool Predicate(item);
```

Example of **incorrect** code:
```dart
abstract class Predicate {
 bool test(item);
}
```

## Further Reading

* [Linter for Dart - one_member_abstracts](https://dart.dev/tools/linter-rules/one_member_abstracts)
* [Effective Dart](https://dart.dev/guides/language/effective-dart/style/)