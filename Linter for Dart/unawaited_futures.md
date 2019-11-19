Pattern: Unawaited `Future`

Issue: -

## Description

**DO** await functions that return a `Future` inside of an async function body.

It's easy to forget `await` in async methods as naming conventions usually don't
tell us if a method is sync or async (except for some in `dart:io`).

When you really _do_ want to start a fire-and-forget `Future`, the recommended
way is to use `unawaited` from `package:pedantic`. The `// ignore` and
`// ignore_for_file` comments also work.

Example of **correct** code:
```dart
Future doSomething() => ...;

void main() async {
 await doSomething();

 unawaited(doSomething()); // Explicitly-ignored fire-and-forget.
}
```

Example of **incorrect** code:
```dart
void main() async {
 doSomething(); // Likely a bug.
}
```

## Further Reading

* [Linter for Dart - unawaited_futures](https://dart-lang.github.io/linter/lints/unawaited_futures.html)