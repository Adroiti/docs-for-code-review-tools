Pattern: Slow compare with block

Issue: -

## Description

This rule identifies places where `sort { |a, b| a.foo <=> b.foo }` can be replaced by `sort_by(&:foo)`. This rule also checks `max` and `min` methods.

## Examples

```ruby
# bad
array.sort { |a, b| a.foo <=> b.foo }
array.max { |a, b| a.foo <=> b.foo }
array.min { |a, b| a.foo <=> b.foo }
array.sort { |a, b| a[:foo] <=> b[:foo] }

# good
array.sort_by(&:foo)
array.sort_by { |v| v.foo }
array.sort_by do |var|
  var.foo
end
array.max_by(&:foo)
array.min_by(&:foo)
array.sort_by { |a| a[:foo] }
```

## Further Reading

* [RuboCop - Performance/CompareWithBlock](https://github.com/rubocop-hq/rubocop-performance/blob/master/manual/cops_performance.md#performancecomparewithblock)
