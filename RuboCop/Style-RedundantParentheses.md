Pattern: Redundant parentheses

Issue: -

## Description

This rule checks for redundant parentheses.

## Examples

```ruby
# bad
(x) if ((y.z).nil?)

# good
x if y.z.nil?
```

## Further Reading

* [RuboCop - Style/RedundantParentheses](https://rubocop.readthedocs.io/en/latest/cops_style/#styleredundantparentheses)
