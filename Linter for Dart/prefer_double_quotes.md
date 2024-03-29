Pattern: Missing use of double quotes

Issue: -

## Description

**DO** use double quotes where they wouldn't require additional escapes.

That means strings with a double quote may use apostrophes so that the double
quote isn't escaped (note: we don't lint the other way around, ie, a double
quoted string with an escaped double quote is not flagged).

It's also rare, but possible, to have strings within string interpolations. In
this case, its much more readable to use a single quote somewhere. So single
quotes are allowed either within, or containing, an interpolated string literal.
Arguably strings within string interpolations should be its own type of lint.

Example of **incorrect** code:
```dart
useStrings(
  'should be double quote',
  r'should be double quote',
  r\'''should be double quotes\''')
```

Example of **correct** code:
```dart
useStrings(
  "should be double quote",
  r"should be double quote",
  r"""should be double quotes""",
  'ok with " inside',
  'nested \${a ? "strings" : "can"} be wrapped by a double quote',
  "and nested \${a ? 'strings' : 'can be double quoted themselves'}");
```

## Further Reading

* [Linter for Dart - prefer_double_quotes](https://dart.dev/tools/linter-rules/prefer_double_quotes)