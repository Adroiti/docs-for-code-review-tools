Pattern: Missing use of `last(n).reverse`/`last`

Issue: -

## Description

Identifies places where `reverse.first(n)` and `reverse.first` can be replaced by `last(n).reverse` and `last`.

## Examples

```ruby
# bad
array.reverse.first(5)
array.reverse.first

# good
array.last(5).reverse
array.last
```

## Further Reading

* [RuboCop - Performance/ReverseFirst](https://docs.rubocop.org/rubocop-performance/cops_performance.html#performancereversefirst)