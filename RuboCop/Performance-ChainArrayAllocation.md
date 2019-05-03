Pattern: Extra array allocation

Issue: -

## Description

`compact`, `flatten` or `map` will generate a new intermediate array that is promptly thrown away. Instead it is faster to mutate when we know it's safe.

### Examples

```ruby
# bad
array = ["a", "b", "c"]
array.compact.flatten.map { |x| x.downcase }
```
```ruby
# good.
array = ["a", "b", "c"]
array.compact!
array.flatten!
array.map! { |x| x.downcase }
array
```

## Further Reading

* [RuboCop - Performance/ChainArrayAllocation](https://github.com/rubocop-hq/rubocop-performance/blob/master/manual/cops_performance.md#performancechainarrayallocation)
