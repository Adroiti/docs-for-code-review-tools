Pattern: Trailing comma in argument list

Issue: -

## Description

This rule checks for trailing comma in argument lists.

## Examples

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

* [RuboCop - Style/TrailingCommaInArguments](https://docs.rubocop.org/rubocop/cops_style.html#styletrailingcommainarguments)
* [https://github.com/bbatsov/ruby-style-guide#no-trailing-params-comma](https://github.com/bbatsov/ruby-style-guide#no-trailing-params-comma)
