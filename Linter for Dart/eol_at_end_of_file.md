Pattern: Missing newline for end of file

Issue: -

## Description

**DO** put a single newline at the end of non-empty files.

Example of **incorrect** code:

```dart
a {
}
```

Example of **correct** code:

```dart
b {
}
  <-- newline
```

## Further Reading

* [Linter for Dart - eol_at_end_of_file](https://dart-lang.github.io/linter/lints/eol_at_end_of_file.html)