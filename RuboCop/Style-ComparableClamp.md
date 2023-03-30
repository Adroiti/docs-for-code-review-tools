Pattern: Missing use of `Comparable#clamp`

Issue: -

## Description

Enforces the use of `Comparable#clamp` instead of comparison by minimum and maximum.

This rule supports autocorrection for `if/elsif/else` bad style only. Because `ArgumentError` occurs if the minimum and maximum of clamp arguments are reversed.

## Examples

```ruby
# bad
[[x, low].max, high].min

# bad
if x < low
  low
elsif high < x
  high
else
  x
end

# good
x.clamp(low, high)
```

## Further Reading

* [RuboCop - Style/ComparableClamp](https://docs.rubocop.org/rubocop/cops_style.html#stylecomparableclamp)