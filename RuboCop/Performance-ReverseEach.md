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

* [RuboCop - Performance/ReverseEach](https://docs.rubocop.org/rubocop-performance/cops_performance.html#performancereverseeach)
* [https://github.com/JuanitoFatas/fast-ruby#enumerablereverseeach-vs-enumerablereverse_each-code](https://github.com/JuanitoFatas/fast-ruby#enumerablereverseeach-vs-enumerablereverse_each-code)
