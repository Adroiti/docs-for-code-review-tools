Pattern: Unsorted unnamed constructors

Issue: -

## Description

**DO** sort unnamed constructor declarations first, before named ones.

Example of **correct** code:
```dart
abstract class CancelableFuture<T> implements Future<T> {
 factory CancelableFuture(computation()) => ...
 factory CancelableFuture.delayed(Duration duration, [computation()]) => ...
 ...
}
```

Example of **incorrect** code:
```dart
class _PriorityItem {
 factory _PriorityItem.forName(bool isStatic, String name, _MemberKind kind) => ...
 _PriorityItem(this.isStatic, this.kind, this.isPrivate);
 ...
}
```

## Further Reading

* [Linter for Dart - sort_unnamed_constructors_first](https://dart-lang.github.io/linter/lints/sort_unnamed_constructors_first.html)