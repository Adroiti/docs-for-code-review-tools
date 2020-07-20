Pattern: Redundant fetch block

Issue: -

## Description

Identifies places where `fetch(key) { value }` can be replaced by `fetch(key, value)`.

In such cases `fetch(key, value)` method is faster than `fetch(key) { value }`.

## Examples

```ruby
# bad
hash.fetch(:key) { 5 }
hash.fetch(:key) { true }
hash.fetch(:key) { nil }
array.fetch(5) { :value }
ENV.fetch(:key) { 'value' }

# good
hash.fetch(:key, 5)
hash.fetch(:key, true)
hash.fetch(:key, nil)
array.fetch(5, :value)
ENV.fetch(:key, 'value')
```

## Further Reading

* [RuboCop - Style/RedundantFetchBlock](https://docs.rubocop.org/rubocop/cops_style.html#styleredundantfetchblock)
