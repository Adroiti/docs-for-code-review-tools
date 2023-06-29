Pattern: Unnecessary null check

Issue: -

## Description

Don't apply a null check when a nullable value is accepted.

Example of **incorrect** code:

```dart
f(int? i);
m() {
 int? j;
 f(j!);
}

```

Example of **correct** code:

```dart
f(int? i);
m() {
 int? j;
 f(j);
}
```

## Further Reading

* [Linter for Dart - unnecessary_null_checks](https://dart.dev/tools/linter-rules/unnecessary_null_checks)