Pattern: Missing use of `DecoratedBox`

Issue: -

## Description

**DO** use `DecoratedBox` when `Container` has only a `Decoration`.

A `Container` is a heavier Widget than a `DecoratedBox`, and as bonus,
`DecoratedBox` has a `const` constructor.

Example of **incorrect** code:
```dart
Widget buildArea() {
 return Container(
  decoration: const BoxDecoration(
   color: Colors.blue,
   borderRadius: BorderRadius.all(
    Radius.circular(5),
   ),
  ),
  child: const Text('...'),
 );
}
```

Example of **correct** code:
```dart
Widget buildArea() {
 return const DecoratedBox(
  decoration: BoxDecoration(
   color: Colors.blue,
   borderRadius: BorderRadius.all(
    Radius.circular(5),
   ),
  ),
  child: Text('...'),
 );
}
```

## Further Reading

* [Linter for Dart - use_decorated_box](https://dart.dev/tools/linter-rules/use_decorated_box)