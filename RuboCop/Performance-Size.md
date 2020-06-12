Pattern: Use of `count` instead of `size`

Issue: -

## Description

This rule is used to identify usages of `count` on an `Array` and `Hash` and change them to `size`.

## Examples

```ruby
# bad
[1, 2, 3].count

# bad
{a: 1, b: 2, c: 3}.count

# good
[1, 2, 3].size

# good
{a: 1, b: 2, c: 3}.size

# good
[1, 2, 3].count { |e| e > 2 }
```

## Further Reading

* [RuboCop - Performance/Size](https://docs.rubocop.org/rubocop-performance/cops_performance.html#performancesize)
* [https://github.com/JuanitoFatas/fast-ruby#arraycount-vs-arraysize-code](https://github.com/JuanitoFatas/fast-ruby#arraycount-vs-arraysize-code)
