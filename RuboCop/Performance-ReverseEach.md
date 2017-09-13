Pattern: Performance/ReverseEach

Issue: -

## Description

This cop is used to identify usages of `reverse.each` and
change them to use `reverse_each` instead.

### Example

```ruby
# bad
[].reverse.each

# good
[].reverse_each
```

## Further Reading

* [RuboCop - Performance/ReverseEach](https://rubocop.readthedocs.io/en/latest/cops_performance/#performancereverseeach)
* [https://github.com/JuanitoFatas/fast-ruby#enumerablereverseeach-vs-enumerablereverse_each-code](https://github.com/JuanitoFatas/fast-ruby#enumerablereverseeach-vs-enumerablereverse_each-code)
