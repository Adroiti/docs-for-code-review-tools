Pattern: Use of `Null` instead of `void`

Issue: -

## Description

**DO NOT** use the type `Null` where `void` would work.

Example of **incorrect** code:
```dart
Null f() {}
Future<Null> f() {}
Stream<Null> f() {}
f(Null x) {}
```

Example of **correct** code:
```dart
void f() {}
Future<void> f() {}
Stream<void> f() {}
f(void x) {}
```

Some exceptions include formulating special function types:

```
Null Function(Null, Null);
```

and for making empty literals which are safe to pass into read-only locations
for any type of map or list:

```
<Null>[];
<int, Null>{};
```

## Further Reading

* [Linter for Dart - prefer_void_to_null](https://dart.dev/tools/linter-rules/prefer_void_to_null)