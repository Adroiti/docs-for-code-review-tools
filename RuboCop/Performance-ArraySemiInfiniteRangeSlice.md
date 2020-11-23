Pattern: Missing use of `Array#take`/`Array#drop`

Issue: -

## Description

Identifies places where slicing arrays with semi-infinite ranges can be replaced by `Array#take` and `Array#drop`.

## Examples

```ruby
# bad
# array[..2]
# array[...2]
# array[2..]
# array[2...]
# array.slice(..2)

# good
array.take(3)
array.take(2)
array.drop(2)
array.drop(2)
array.take(3)
```

## Further Reading

* [RuboCop - Performance/ArraySemiInfiniteRangeSlice](https://docs.rubocop.org/rubocop-performance/cops_performance.html#performancearraysemiinfiniterangeslice)