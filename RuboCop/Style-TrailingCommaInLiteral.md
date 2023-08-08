Pattern: Trailing comma in `Array`/`Hash` literal

Issue: -

## Description

This rule checks for trailing comma in array and hash literals.

## Examples

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

* [RuboCop - Style/TrailingCommaInLiteral](https://docs.rubocop.org/rubocop/cops_style.html#styletrailingcommainliteral)
* [https://github.com/bbatsov/ruby-style-guide#no-trailing-array-commas](https://github.com/bbatsov/ruby-style-guide#no-trailing-array-commas)
