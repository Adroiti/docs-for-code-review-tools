Pattern: Style/TrailingCommaInArguments

Issue: -

## Description

This cop checks for trailing comma in argument lists.

### Example

```ruby
# always bad
method(1, 2,)

# good if EnforcedStyleForMultiline is consistent_comma
method(
  1, 2,
  3,
)

# good if EnforcedStyleForMultiline is comma or consistent_comma
method(
  1,
  2,
)

# good if EnforcedStyleForMultiline is no_comma
method(
  1,
  2
)
```

## Default configuration

Attribute | Value
--- | ---
EnforcedStyleForMultiline | no_comma
SupportedStylesForMultiline | comma, consistent_comma, no_comma

## Further Reading

* [RuboCop - Style/TrailingCommaInArguments](https://rubocop.readthedocs.io/en/latest/cops_style/#styletrailingcommainarguments)
* [https://github.com/bbatsov/ruby-style-guide#no-trailing-params-comma](https://github.com/bbatsov/ruby-style-guide#no-trailing-params-comma)
