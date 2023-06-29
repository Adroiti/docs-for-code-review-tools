Pattern: Missing documentation for public member

Issue: -

## Description

All non-overriding public members should be documented with `///` doc-style comments.

Example of **correct** code:
```dart
/// A good thing.
abstract class Good {
 /// Start doing your thing.
 void start() => _start();

 _start();
}
```

Example of **incorrect** code:
```dart
class Bad {
 void meh() { }
}
```

In case a public member overrides a member it is up to the declaring member
to provide documentation. For example, in the following, `Sub` needn't
document `init` (though it certainly may, if there's need).

Example of **correct** code:
```dart
/// Base of all things.
abstract class Base {
 /// Initialize the base.
 void init();
}

/// A sub base.
class Sub extends Base {
 @override
 void init() { ... }
}
```

Note that consistent with `dartdoc`, an exception to the rule is made when
documented getters have corresponding undocumented setters. In this case the
setters inherit the docs from the getters.

## Further Reading

* [Linter for Dart - public_member_api_docs](https://dart.dev/tools/linter-rules/public_member_api_docs)