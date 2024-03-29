Pattern: Missing use of single quotes

Issue: -

## Description

**DO** use single quotes where they wouldn't require additional escapes.

That means strings with an apostrophe may use double quotes so that the
apostrophe isn't escaped (note: we don't lint the other way around, ie, a single
quoted string with an escaped apostrophe is not flagged).

It's also rare, but possible, to have strings within string interpolations. In
this case, its much more readable to use a double quote somewhere. So double
quotes are allowed either within, or containing, an interpolated string literal.
Arguably strings within string interpolations should be its own type of lint.

Example of **incorrect** code:
```dart
useStrings(
  "should be single quote",
  r"should be single quote",
  r"""should be single quotes""")
```

Example of **correct** code:
```dart
useStrings(
  'should be single quote',
  r'should be single quote',
  r\'''should be single quotes\''',
  "here's ok",
  "nested \${a ? 'strings' : 'can'} be wrapped by a double quote",
  'and nested \${a ? "strings" : "can be double quoted themselves"}');
```

## Further Reading

* [Linter for Dart - prefer_single_quotes](https://dart.dev/tools/linter-rules/prefer_single_quotes)