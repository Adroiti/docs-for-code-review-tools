Pattern: Use of `reverse.each`

Issue: -

## Description

This rule is used to identify usages of `reverse.each` and change them to use `reverse_each` instead.

## Examples

```ruby
# bad
[].reverse.each

# good
[].reverse_each
```

## Further Reading

* [RuboCop - Performance/ReverseEach](https://github.com/rubocop-hq/rubocop-performance/blob/master/manual/cops_performance.md#performancereverseeach)
* [https://github.com/JuanitoFatas/fast-ruby#enumerablereverseeach-vs-enumerablereverse_each-code](https://github.com/JuanitoFatas/fast-ruby#enumerablereverseeach-vs-enumerablereverse_each-code)
