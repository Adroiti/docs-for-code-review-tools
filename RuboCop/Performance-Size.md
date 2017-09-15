Pattern: Use of `count` instead of `size`

Issue: -

## Description

This cop is used to identify usages of `count` on an `Array` and `Hash` and change them to `size`.

### Example

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

* [RuboCop - Performance/Size](https://rubocop.readthedocs.io/en/latest/cops_performance/#performancesize)
* [https://github.com/JuanitoFatas/fast-ruby#arraycount-vs-arraysize-code](https://github.com/JuanitoFatas/fast-ruby#arraycount-vs-arraysize-code)
