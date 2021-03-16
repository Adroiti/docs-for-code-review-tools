Pattern: Redundant equality comparison block

Issue: -

## Description

Checks if `Enumerable#all?`, `Enumerable#any?`, `Enumerable#one?`, and `Enumerable#none?` are compared with `===` or similar methods in block.

By default, `Object#===` behaves the same as `Object#==`, but this behavior is appropriately overridden in subclass. For example, `Range#===` returns true when argument is within the range. Therefore, It is marked as unsafe by default because `===` and `==` do not always behave the same.

## Examples

```ruby
# bad
items.all? { |item| pattern === item }
items.all? { |item| item == other }
items.all? { |item| item.is_a?(Klass) }
items.all? { |item| item.kind_of?(Klass) }

# good
items.all?(pattern)
```

## Further Reading

* [RuboCop - Performance/RedundantEqualityComparisonBlock](https://docs.rubocop.org/rubocop-performance/cops_performance.html#performanceredundantequalitycomparisonblock)
