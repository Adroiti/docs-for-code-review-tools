Pattern: Style/TrailingCommaInLiteral

Issue: -

## Description

This cop checks for trailing comma in array and hash literals.

### Example

```ruby
# always bad
a = [1, 2,]

# good if EnforcedStyleForMultiline is consistent_comma
a = [
  1, 2,
  3,
]

# good if EnforcedStyleForMultiline is comma or consistent_comma
a = [
  1,
  2,
]

# good if EnforcedStyleForMultiline is no_comma
a = [
  1,
  2
]
```

## Default configuration

Attribute | Value
--- | ---
EnforcedStyleForMultiline | no_comma
SupportedStylesForMultiline | comma, consistent_comma, no_comma

## Further Reading

* [RuboCop - Style/TrailingCommaInLiteral](https://rubocop.readthedocs.io/en/latest/cops_style/#styletrailingcommainliteral)
* [https://github.com/bbatsov/ruby-style-guide#no-trailing-array-commas](https://github.com/bbatsov/ruby-style-guide#no-trailing-array-commas)
