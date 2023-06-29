Pattern: Missing use of `if` for collection building

Issue: -

## Description

When building collections, it is preferable to use `if` elements rather than
conditionals.

Example of **incorrect** code:
```dart
Widget build(BuildContext context) {
 return Row(
  children: [
   IconButton(icon: Icon(Icons.menu)),
   Expanded(child: title),
   isAndroid ? IconButton(icon: Icon(Icons.search)) : null,
  ].where((child) => child != null).toList(),
 );
}
```

Example of **correct** code:
```dart
Widget build(BuildContext context) {
 return Row(
  children: [
   IconButton(icon: Icon(Icons.menu)),
   Expanded(child: title),
   if (isAndroid) IconButton(icon: Icon(Icons.search)),
  ]
 );
}

## Further Reading

* [Linter for Dart - prefer_if_elements_to_conditional_expressions](https://dart.dev/tools/linter-rules/prefer_if_elements_to_conditional_expressions)