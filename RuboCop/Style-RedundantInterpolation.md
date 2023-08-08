Pattern: Redundant string interpolation

Issue: -

## Description

This rule checks for strings that are just an interpolated expression.

## Examples

```ruby
# bad
"#{@var}"

# good
@var.to_s

# good if @var is already a String
@var
```

## Further Reading

* [RuboCop - Style/RedundantInterpolation](https://docs.rubocop.org/rubocop/cops_style.html#styleredundantinterpolation)
