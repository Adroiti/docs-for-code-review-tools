Pattern: Returning null for `void`

Issue: -

## Description

In a large variety of languages `void` as return type is used to indicate that
a function doesn't return anything. Dart allows returning `null` in functions
with `void` return type but it also allow using `return;` without specifying any
value. To have a consistent way you should not return `null` and only use an
empty return.

Example of **incorrect** code:
```dart
void f1() {
 return null;
}
Future<void> f2() async {
 return null;
}
```

Example of **correct** code:
```dart
void f1() {
 return;
}
Future<void> f2() async {
 return;
}
```

## Further Reading

* [Linter for Dart - avoid_returning_null_for_void](https://dart.dev/tools/linter-rules/avoid_returning_null_for_void)