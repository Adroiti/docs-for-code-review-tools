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

* [RuboCop - Style/RedundantParentheses](https://docs.rubocop.org/rubocop/cops_style.html#styleredundantparentheses)
