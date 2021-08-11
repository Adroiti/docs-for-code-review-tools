Pattern: Use of `select.map` instead of `filter_map`

Issue: -

## Description

In Ruby 2.7, `Enumerable#filter_map` has been added.

This rule identifies places where `select.map` can be replaced by `filter_map`.

## Examples

```ruby
# bad
ary.select(&:foo).map(&:bar)
ary.filter(&:foo).map(&:bar)

# good
ary.filter_map { |o| o.bar if o.foo }
```

## Further Reading

* [RuboCop - Performance/SelectMap](https://docs.rubocop.org/rubocop-performance/cops_performance.html#performanceselectmap)
