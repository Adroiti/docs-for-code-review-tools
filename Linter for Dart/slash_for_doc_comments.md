Pattern: Missing use of `///` for doc comment

Issue: -

## Description

Although Dart supports two syntaxes of doc comments (`///` and `/**`), we prefer using `///` for doc comments.

Example of **correct** code:
```dart
/// Parses a set of option strings. For each option:
///
/// * If it is `null`, then it is ignored.
/// * If it is a string, then [validate] is called on it.
/// * If it is any other type, it is *not* validated.
void parse(List options) {
 // ...
}
```

Within a doc comment, you can use markdown for formatting.

## Further Reading

* [Linter for Dart - slash_for_doc_comments](https://dart-lang.github.io/linter/lints/slash_for_doc_comments.html)