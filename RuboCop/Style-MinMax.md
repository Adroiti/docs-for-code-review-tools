Pattern: Min max

Issue: -

## Description

This cop checks for potential uses of `Enumerable#minmax`.

### Example

```ruby
# bad
bar = [foo.min, foo.max]
return foo.min, foo.max

# good
bar = foo.minmax
return foo.minmax
```

## Further Reading

* [RuboCop - Style/MinMax](https://rubocop.readthedocs.io/en/latest/cops_style/#styleminmax)
