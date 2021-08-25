Pattern: Malformed qouted symbol

Issue: -

## Description

Checks if the quotes used for quoted symbols match the configured defaults. By default uses the same configuration as `Style/StringLiterals`.

String interpolation is always kept in double quotes.

## Examples

EnforcedStyle: same_as_string_literals (default) / single_quotes

```ruby
# bad
:"abc-def"

# good
:'abc-def'
:"#{str}"
:"a\'b"
```

EnforcedStyle: double_quotes

```ruby
# bad
:'abc-def'

# good
:"abc-def"
:"#{str}"
:"a\'b"
```

## Further Reading

* [RuboCop - Style/QuotedSymbols](https://docs.rubocop.org/rubocop/cops_style.html#stylequotedsymbols)