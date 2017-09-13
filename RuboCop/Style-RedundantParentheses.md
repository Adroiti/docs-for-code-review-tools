Pattern: Style/RedundantParentheses

Issue: -

## Description

This cop checks for redundant parentheses.

### Example

```ruby
# bad
(x) if ((y.z).nil?)

# good
x if y.z.nil?
```

## Further Reading

* [RuboCop - Style/RedundantParentheses](https://rubocop.readthedocs.io/en/latest/cops_style/#styleredundantparentheses)
