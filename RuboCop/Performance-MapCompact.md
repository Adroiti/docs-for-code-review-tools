Pattern: Use of `map { …​ }.compact` instead of `filter_map`

Issue: -

## Description

In Ruby 2.7, `Enumerable#filter_map` has been added.

This rule identifies places where `map { …​ }.compact` can be replaced by `filter_map`. It is marked as unsafe auto-correction by default because `map { …​ }.compact` that is not compatible with `filter_map`.


## Examples

```ruby
# bad
ary.map(&:foo).compact
ary.collect(&:foo).compact

# good
ary.filter_map(&:foo)
ary.map(&:foo).compact!
ary.compact.map(&:foo)
```

## Further Reading

* [RuboCop - Performance/MapCompact](https://docs.rubocop.org/rubocop-performance/cops_performance.html#performancemapcompact)
