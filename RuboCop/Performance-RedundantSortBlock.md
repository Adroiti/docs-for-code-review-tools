Pattern: Redundant sort block

Issue: -

## Description

Identifies places where `sort { |a, b| a <⇒ b }` can be replaced with `sort`.

## Examples

```ruby
# bad
array.sort { |a, b| a <=> b }

# good
array.sort
```

## Further Reading

* [RuboCop - Performance/RedundantSortBlock](https://docs.rubocop.org/rubocop-performance/cops_performance.html#performanceredundantsortblock)