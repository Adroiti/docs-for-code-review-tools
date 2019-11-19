Pattern: Use of unnecessary `Container`

Issue: -

## Description

Wrapping a widget in `Container` with no other parameters set has no effect and makes code needlessly more complex.

Example of **incorrect** code:
```dart
Widget buildRow() {
 return Container(
   child: Row(
    children: <Widget>[
     const MyLogo(),
     const Expanded(
      child: Text('...'),
     ),
    ],
   )
 );
}
```

Example of **correct** code:
```dart
Widget buildRow() {
 return Row(
  children: <Widget>[
   const MyLogo(),
   const Expanded(
    child: Text('...'),
   ),
  ],
 );
}
```

## Further Reading

* [Linter for Dart - avoid_unnecessary_containers](https://dart-lang.github.io/linter/lints/avoid_unnecessary_containers.html)