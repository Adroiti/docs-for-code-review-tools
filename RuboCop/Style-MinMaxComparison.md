Pattern: Missing use of `max`/`min`

Issue: -

## Description

Enforces the use of `max` or `min` instead of comparison for greater or less.

NOTE: It can be used if you want to present limit or threshold in Ruby 2.7+.
That it is slow though. So auto-correction will apply generic `max` or `min`:

```ruby
a.clamp(b..) # Same as `[a, b].max`
a.clamp(..b) # Same as `[a, b].min`
```

## Examples

```ruby
# bad
a > b ? a : b
a >= b ? a : b

# good
[a, b].max

# bad
a < b ? a : b
a <= b ? a : b

# good
[a, b].min
```

## Further Reading

* [RuboCop - Style/MinMaxComparison](https://docs.rubocop.org/rubocop/cops_style.html#styleminmaxcomparison)
