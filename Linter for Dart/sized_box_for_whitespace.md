Pattern: Missing use of `SizedBox` for whitespace

Issue: -

## Description

Use `SizedBox` to add whitespace to a layout.

A `Container` is a heavier Widget than a `SizedBox`, and as bonus, `SizedBox`
has a `const` constructor.

Example of **incorrect** code:

```dart
Widget buildRow() {
 return Row(
  children: <Widget>[
   const MyLogo(),
   Container(width: 4),
   const Expanded(
    child: Text('...'),
   ),
  ],
 );
}
```

Example of **correct** code:

```dart
Widget buildRow() {
 return Row(
  children: const <Widget>[
   MyLogo(),
   SizedBox(width: 4),
   Expanded(
    child: Text('...'),
   ),
  ],
 );
}
```

## Further Reading

* [Linter for Dart - sized_box_for_whitespace](https://dart.dev/tools/linter-rules/sized_box_for_whitespace)