Pattern: Use of `map` in a chain

Issue: -

## Description

Checks if the map method is used in a chain.

Autocorrection is not supported because an appropriate block variable name cannot be determined automatically.

## Examples

```ruby
# bad
array.map(&:foo).map(&:bar)

# good
array.map { |item| item.foo.bar }
```

## Further Reading

* [RuboCop - Performance/MapMethodChain](https://docs.rubocop.org/rubocop-performance/cops_performance.html#performancemapmethodchain)
