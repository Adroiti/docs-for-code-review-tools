Pattern: Use of `SizedBox(...)` constructor

Issue: -

## Description

Use `SizedBox.shrink(...) and SizedBox.expand(...)` constructors appropriately.

The `SizedBox.shrink(...)` and `SizedBox.expand(...)` constructors should be used instead of the more general `SizedBox(...)` constructor when the named constructors capture the intent of the code more succinctly.

Example of **incorrect** code:
```dart
Widget buildLogo() {
 return SizedBox(
  height: 0,
  width: 0,
  child: const MyLogo(),
 );
}
```

```dart
Widget buildLogo() {
 return SizedBox(
  height: double.infinity,
  width: double.infinity,
  child: const MyLogo(),
 );
}
```

Example of **correct** code:
```dart
Widget buildLogo() {
 return SizedBox.shrink(
  child: const MyLogo(),
 );
}
```

```dart
Widget buildLogo() {
 return SizedBox.expand(
  child: const MyLogo(),
 );
}
```

## Further Reading

* [Linter for Dart - sized_box_shrink_expand](https://dart-lang.github.io/linter/lints/sized_box_shrink_expand.html)