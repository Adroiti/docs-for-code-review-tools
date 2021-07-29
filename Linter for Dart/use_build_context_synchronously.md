Pattern: Use of `BuildContext` across asynchronous gaps

Issue: -

## Description

**DO NOT** use BuildContext across asynchronous gaps.

Storing `BuildContext` for later usage can easily lead to difficult to diagnose
crashes. Asynchronous gaps are implicitly storing `BuildContext` and are some of
the easiest to overlook when writing code.

When a `BuildContext` is used from a `StatefulWidget`, the `mounted` property
must be checked after an asynchronous gap.

Example of **correct** code:

```dart
void onButtonTapped(BuildContext context) {
 Navigator.of(context).pop();
}
```

Example of **incorrect** code:

```dart
void onButtonTapped(BuildContext context) async {
 await Future.delayed(const Duration(seconds: 1));
 Navigator.of(context).pop();
}
```

Example of **correct** code:

```dart
class _MyWidgetState extends State<MyWidget> {
 ...

 void onButtonTapped() async {
  await Future.delayed(const Duration(seconds: 1));

  if (!mounted) return;
  Navigator.of(context).pop();
 }
}
```

## Further Reading

* [Linter for Dart - use_build_context_synchronously](https://dart-lang.github.io/linter/lints/use_build_context_synchronously.html)