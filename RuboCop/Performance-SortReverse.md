Pattern: Missing use of `sort.reverse`

Issue: -

## Description

Identifies places where `sort { |a, b| b <⇒ a }` can be replaced by a faster `sort.reverse`.

## Examples

```ruby
# bad
array.sort { |a, b| b <=> a }

# good
array.sort.reverse
```

## Further Reading

* [RuboCop - Performance/SortReverse](https://docs.rubocop.org/rubocop-performance/cops_performance.html#performancesortreverse)