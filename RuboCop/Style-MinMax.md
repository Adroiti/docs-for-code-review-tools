Pattern: Missing use of `Enumerable#minmax`

Issue: -

## Description

This rule checks for potential uses of `Enumerable#minmax`.

## Examples

```ruby
# bad
bar = [foo.min, foo.max]
return foo.min, foo.max

# good
bar = foo.minmax
return foo.minmax
```

## Further Reading

* [RuboCop - Style/MinMax](https://docs.rubocop.org/rubocop/cops_style.html#styleminmax)
