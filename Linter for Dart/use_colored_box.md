Pattern: Missing use of `ColoredBox`

Issue: -

## Description

**DO** use `ColoredBox` when `Container` has only a `Color`.

A `Container` is a heavier Widget than a `ColoredBox`, and as bonus, `ColoredBox` has a `const` constructor.

Example of **incorrect** code:

```dart
Widget buildArea() {
 return Container(
  color: Colors.blue,
  child: const Text('hello'),
 );
}
```

Example of **correct** code:
```dart
Widget buildArea() {
 return const ColoredBox(
  color: Colors.blue,
  child: Text('hello'),
 );
}
```

## Further Reading

* [Linter for Dart - use_colored_box](https://dart-lang.github.io/linter/lints/use_colored_box.html)