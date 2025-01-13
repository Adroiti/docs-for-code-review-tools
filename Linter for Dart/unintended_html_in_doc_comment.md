Pattern: Unintended HTML in doc comment

Issue: -

## Description

Use of angle brackets in a doc comment is treated as HTML by Markdown.

DON'T use angle-bracketed text, `<…>`, in a doc comment unless you want to write an HTML tag or link.

Example of **incorrect** code:

```dart
/// The type List<int>.
/// <assignment> -> <variable> = <expression>
```

Example of **correct** code:

```dart
/// The type `List<int>`.
/// The type [List<int>]
/// `<assignment> -> <variable> = <expression>`
/// \<assignment\> -> \<variable\> = \<expression\>`
/// <http://foo.bar.baz>
```

## Further Reading

* [Linter for Dart - unintended_html_in_doc_comment](https://dart.dev/tools/linter-rules/unintended_html_in_doc_comment)