Pattern: Unneeded string interpolation

Issue: -

## Description

This cop checks for strings that are just an interpolated expression.

### Example

```ruby
# bad
"#{@var}"

# good
@var.to_s

# good if @var is already a String
@var
```

## Further Reading

* [RuboCop - Style/UnneededInterpolation](https://rubocop.readthedocs.io/en/latest/cops_style/#styleunneededinterpolation)
