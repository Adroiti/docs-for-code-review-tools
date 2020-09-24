Pattern: Missing use of `Enumerable#sum`

Issue: -

## Description

This rule identifies places where custom code finding the sum of elements in some Enumerable object can be replaced by `Enumerable#sum` method.

## Examples

```ruby
# bad
[1, 2, 3].inject(:+)
[1, 2, 3].reduce(10, :+)
[1, 2, 3].inject(&:+)
[1, 2, 3].reduce { |acc, elem| acc + elem }

# good
[1, 2, 3].sum
[1, 2, 3].sum(10)
[1, 2, 3].sum
```

## Further Reading

* [RuboCop - Performance/Sum](https://docs.rubocop.org/rubocop-performance/cops_performance.html#performancesum)